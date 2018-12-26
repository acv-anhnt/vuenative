<template>
  <View class="containerStyle">
      <flat-list
        :data="listViewData"
        :render-item="(item) => renderList(item)"
        ref="listabc"
        inverted
    />
    <View class="footer">
      <TextInput v-model="newMessage" />
      <Button title="Send" :onPress="sendMessage" />
    </View>
  </View>

</template>
<script>
import React from "react";
import { ListView, FlatList } from "react-native";
import { Button, Icon, Text, ListItem } from "native-base";
export default {
  data: function() {
    return {
      ds: new ListView.DataSource({ rowHasChanged: (r1, r2) => r1 !== r2 }),
      basic: true,
      newMessage: "",
      flatlistdata: [
        { name: "Movies", header: true },
        { name: "Interstellar", header: false },
        { name: "Dark Knight", header: false },
        { name: "Pop", header: false },
        { name: "Pulp Fiction", header: false },
        { name: "Burning Train", header: false },
        { name: "Music", header: true },
        { name: "Adams", header: false },
        { name: "Nirvana", header: false },
        { name: "Amrit Maan", header: false },
        { name: "Oye Hoye", header: false },
        { name: "Eminem", header: false },
        { name: "Places", header: true },
        { name: "Jordan", header: false },
        { name: "Punjab", header: false },
        { name: "Ludhiana", header: false },
        { name: "Jamshedpur", header: false },
        { name: "India", header: false },
        { name: "People", header: true },
        { name: "Jazzy", header: false },
        { name: "Appie", header: false },
        { name: "Baby", header: false },
        { name: "Sunil", header: false },
        { name: "Arrow", header: false },
        { name: "Things", header: true },
        { name: "table", header: false },
        { name: "chair", header: false },
        { name: "fan", header: false },
        { name: "cup", header: false },
        { name: "cube", header: false }
      ],
      listViewData: [
        "Simon Mignolet",
        "Nathaniel Clyne",
        "Dejan Lovren",
        "Mama Sakho",
        "Alberto Moreno",
        "Emre Can",
        "Joe Allen"
      ]
    };
  },
  mounted: function() {
    alert("Mouted")

  },
  methods: {
            renderList: function(item) {
                return (<Text>{item.item}</Text>)
            },
    sendMessage: function(){
      this.listViewData.unshift(this.newMessage);
    },
    deleteRow: function(secId, rowId, rowMap) {
      rowMap[`${secId}${rowId}`].props.closeRow();
      const newData = [...this.listViewData];
      newData.splice(rowId, 1);
      this.listViewData = newData;
    },
    getLeftHiddenRowComponet: function(data) {
      return (
        <Button full onPress={() => alert(data)}>
          <Icon active name="information-circle" />
        </Button>
      );
    },
    getRighttHiddenRowComponet: function(data, secId, rowId, rowMap) {
      return (
        <Button full danger onPress={_ => this.deleteRow(secId, rowId, rowMap)}>
          <Icon active name="trash" />
        </Button>
      );
    },
    getListArr: function() {
      return this.ds.cloneWithRows(this.listViewData);
    },
    getListItemRow: function(data) {
      return (
        <ListItem>
          <Text>{data}</Text>
        </ListItem>
      );
    }
  }
};
</script>
<style scoped>
.reverseContent {
  transform: scaleY(-1);
}
.chatList{
  transform: scaleY(1);
}
.containerStyle{
  flex: 1;
  margin-top: 20px;
}
.footer{
  background-color: grey;
}
</style>
