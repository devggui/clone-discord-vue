<template>
  <div class="statusItem">
    <div
      :class="{
        'icon-online': online,
        'icon-absent': absent,
        'icon-notDisturb': notDisturb,
        'icon-invisible': invisible,
        'icon-custom': custom
      }"
    ></div>
    <div class="statusdata">
      <div class="status">
        {{ statusName }}
      </div>
      <div class="description">
        {{ description }}
      </div>
    </div>
  </div>

</template>

<script>
  export default {
    props: {
      online: Boolean,
      absent: Boolean,
      notDisturb: Boolean,
      invisible: Boolean,
      custom: Boolean,
      statusName: String,
      description: String
    }
  }
</script>

<style scoped lang="scss">

  .statusItem {
    display: grid;
    grid-template-columns: 24px 1fr;
    width: 100%;
    align-items: center;
    padding: 4px 8px;
    min-height: 24px;
    -webkit-box-align: center;

    &:hover {
      background-color: white;
    }
  }

  .icon-online {
    display: flex;
    flex-direction: row;
    background: #3BA55D;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .icon-absent {
    display: flex;
    flex-direction: row;
    background: black;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .icon-notDisturb {
    display: flex;
    flex-direction: row;
    background: yellow;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .icon-invisible {
    display: flex;
    flex-direction: row;
    background: white;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .icon-custom {
    display: flex;
    flex-direction: row;
    background: blue;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .separator {
    border-bottom: solid 1px hsla(0,0%,100%,0.06);;
  }

  .statusdata {
    display: flex;
    flex-direction: column;

    .status {
      color: #B9BBBE;
      font-size: 14px;
    }

    .description {
      font-size: 12px;
      margin: 0 0 2px;
      color: #B9BBBE;
    }
  }

</style>
