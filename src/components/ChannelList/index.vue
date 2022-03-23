<template>
  <div class="channel-list">
    <div class="category">
      <div>Canais de Texto</div>
      <div class="category-icon">
        <AddCategoryIcon :size="21"/>
      </div>
    </div>
    <ChannelButton selected channelName="naruto" />
    <ChannelButton channelName="csgo" />
    <ChannelButton channelName="lol" />
    <ChannelButton channelName="amongus" />
    <ChannelButton channelName="naruto" />
    <ChannelButton channelName="dragonball" />
    <UserStatus v-if="showUserStatus" />
  </div>
</template>

<script>
  import AddCategoryIcon from 'vue-material-design-icons/Plus'
  import ChannelButton from './ChannelButton'
  import UserStatus from '../UserInfo/UserStatus'

  export default {
    components: {
      AddCategoryIcon,
      ChannelButton,
      UserStatus
    },

    /*
    <UserStatus v-if="showUserStatus" />
    Valor padrão do dado por referência: false
    Componente recebe false como dado
    */
    data() {
      return {
        showUserStatus: false,
      }
    }
  }

</script>

<style scoped lang="scss">
  .channel-list {
    grid-area: CL;
    display: flex;
    flex-direction: column;
    padding: 24px 10px 0 16px;
    background-color: var(--secondary);
  }

  .category {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 6px;
    color: var(--gray);
    font-size: 12px;
    font-weight: bold;
    text-transform: uppercase;
  }

  .category-icon {
    color: var(--symbol);
    cursor: pointer;
  }

</style>
