<template>
  <div class="container">
    <div class="profile">
      <div class="avatar" @click="handleClick">
        <div class="status" @selected="toggleIconStatus"></div>
      </div>
      <div class="userdata">
        <strong>Guilherme</strong>
        <span>#1234</span>
      </div>
    </div>
    <div class="actions">
      <Mic :size="20"/>
      <HeadPhones :size="20"/>
      <Settings :size="20"/>
    </div>
  </div>
</template>

<script>
  import Mic from 'vue-material-design-icons/Microphone'
  import HeadPhones from 'vue-material-design-icons/Headphones'
  import Settings from 'vue-material-design-icons/CogOutline'
  import UserStatus from './UserStatus'

  export default {
    components: {
      Mic,
      HeadPhones,
      Settings,
      UserStatus
    },

    /*
    <div class="avatar" @click="handleClick"> <- Toda vez que a div avatar for clicada,
    será emitido um parâmetro 'click'.
    */
    methods: {
      handleClick() {
        this.$emit('click');
      },

      toggleIconStatus() {
        //Faz algo...
      }
    }
  }

</script>

<style scoped lang="scss">
  .container {
    grid-area: UI;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    background-color: var(--quaternary);
    padding: 10px;
    box-shadow: rgba(0, 0, 0, 0.2) 0 1px 0 0;
  }

  .profile {
    display: flex;
    align-items: center;
  }

  .avatar {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background-color: var(--gray);
    position: relative;
    display: flex;
    flex-direction: column;

    .status {
      /* background-color: var(--notification); */
      width: auto;
      height: 16px;
      padding: 0 4px;
      position: absolute;
      bottom: -4px;
      right: -4px;
      border: solid 4px var(--quaternary);
      border-radius: 12px;
      text-align: right;
      font-size: 13px;
      font-weight: bold;
      color: var(--white);
    }
  }

  .userdata {
    display: flex;
    flex-direction: column;
    margin-left: 8px;
    font-size: 13px;

    strong {
      display: block;
      color: var(--white);
    }

    span {
      color: var(--gray);
    }
  }

  .actions {
    color: var(--gray);

    span {
      cursor: pointer;
      transition: 0.2s;

      &:hover {
        color: var(--white);
      }
    }
  }

</style>
