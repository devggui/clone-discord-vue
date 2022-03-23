<template>
  <div id="grid">
    <ServerList />
    <ServerName />
    <ChannelList ref="channel-list" />
    <UserInfo @click="toggleUserStatus" />
  </div>
</template>

<script>
  import ServerList from './ServerList/index'
  import ServerName from './ServerName/index'
  import ChannelList from './ChannelList/index'
  import UserInfo from './UserInfo/index'

  export default {
    components: {
      ServerList,
      ServerName,
      ChannelList,
      UserInfo
    },

    /*
    <ChannelList ref="channel-list" />
    <UserInfo @click="toggleUserStatus" />

    Assim que a pagina index.vue do componente UserInfo emitir que foi clicado,
    será chamado esse método toggleUserStatus -> Dentro dele, irá pegar o componente
    por referência 'channel-list' e alterará o valor dele (que por padrão é false)
    */
    methods: {
      toggleUserStatus() {
        this.$refs['channel-list'].showUserStatus = !this.$refs['channel-list'].showUserStatus;
      }
    }
  }
</script>

<style scoped>
  #grid {
    display: grid;
    height: 100vh;
    grid-template-columns: 71px 240px auto 240px;
    grid-template-rows: 46px auto 52px;
    grid-template-areas:
      'SL SN CI CI'
      'SL CL CD UL'
      'SL UI CD UL'
    ;
  }
</style>
