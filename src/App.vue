<template>
    <!--
    <div v-if="!this.connected"><LoadingScreen /></div>
    <div v-else-if="!this.validIp"><IpError /></div>
    <div v-else-if="!this.validUdid"><UploadUdid /></div>
    <div v-else><JitStore /></div>
    -->
    <div><Setup /></div>
</template>

<script>
// That moment when you literally have 3 different comment syntaxes...
// import IpError from './components/IpError.vue';
// import LoadingScreen from './components/LoadingScreen.vue';
// import JitStore from './components/JitStore.vue';
// import UploadUdid from './components/UploadUdid.vue';
import Setup from './components/Setup.vue';

let NetStack = require('./netstack.js');

export default {
    name: 'App',
    components: {
        // IpError,
        // LoadingScreen,
        // JitStore,
        // UploadUdid,
        Setup,
    },
    beforeCreate() {
        console.log('Starting JitStreamer...');

        NetStack.status(this);
    },
    data() {
        return {
            connected: false,
            validIp: false,
            validUdid: false,
        };
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
img {
    /* make square circle */
    border-radius: 200px;
}
footer {
    position: absolute;
    margin: 0px 0;
    text-align: center;
    font-size: 12px;
    color: darkblue;
}
</style>
