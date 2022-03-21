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
  </div>
</template>

<script>
  import AddCategoryIcon from 'vue-material-design-icons/Plus'
  import ChannelButton from './ChannelButton'

  export default {
    components: {
      AddCategoryIcon,
      ChannelButton
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
