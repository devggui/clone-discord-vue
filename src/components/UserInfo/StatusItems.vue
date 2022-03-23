<template>
  <div class="statusItem">
    <slot name="icon">
      <div class="icons"
        :class="{
          'icon-online': online,
          'icon-absent': absent,
          'icon-notDisturb': notDisturb,
          'icon-invisible': invisible
        }"
      ></div>
    </slot>
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
      statusName: String,
      description: String
    }
  }
</script>

<style scoped lang="scss">

  .statusItem {
    display: grid;
    grid-template-columns: 24px 1fr;
    width: 95%;
    align-items: center;
    padding: 4px 8px;
    margin: 5px;
    min-height: 24px;
    -webkit-box-align: center;

    &:hover {
      background-color: var(--rocketseat);
      border-radius: 4px;
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
    background: #FAA81A;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .icon-notDisturb {
    display: flex;
    flex-direction: row;
    background: #ED4245;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .icon-invisible {
    display: flex;
    flex-direction: row;
    background: #747F8D;
    width: 10px;
    height: 10px;
    border-radius: 50%;
  }

  .icon-custom {
    display: flex;
    flex-direction: row;
    color: #B9BBBE;
    width: 30px;
    height: 30px;
    margin-left: -5px;
    font-size: 14px;
    align-items: center;
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
