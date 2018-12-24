<template>
    <nb-content padder>
        <nb-grid>
        <nb-row :style="{ backgroundColor: '#635DB7' }">
            <nb-col :style="{ backgroundColor: 'red'}">
                <nb-text>NativeBase is open source and free.</nb-text>
            </nb-col>
            <nb-col>
            <nb-row :style="{ backgroundColor: 'yellow'}"></nb-row>
            <nb-row :style="{ backgroundColor: 'green'}"></nb-row>
            </nb-col>
        </nb-row>
        <nb-col :style="{ backgroundColor: '#00CE9F' }"></nb-col>
        </nb-grid>
    </nb-content>
</template>