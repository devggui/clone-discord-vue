<template>
  <div id="grid">
    <ServerList />
    <ServerName />
    <ChannelList />
    <UserInfo />
    <UserStatus />
  </div>
</template>

<script>
  import ServerList from './ServerList/index'
  import ServerName from './ServerName/index'
  import ChannelList from './ChannelList/index'
  import UserInfo from './UserInfo/index'

  //Teste
  import UserStatus from './UserInfo/UserStatus.vue'

  export default {
    components: {
      ServerList,
      ServerName,
      ChannelList,
      UserInfo,
      UserStatus
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
