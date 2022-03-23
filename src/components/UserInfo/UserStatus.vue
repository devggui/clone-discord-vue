<template>
  <div class="container">
    <StatusItems online statusName="Disponível" @click="handleChangeStatusOnline"/>
    <div class="separator"></div>
    <StatusItems absent statusName="Ausente"/>
    <StatusItems notDisturb statusName="Não pertubar" description="Você não irá mais receber notificações na área de trabalho"/>
    <StatusItems invisible statusName="Invisível" description="Você não aparecerá como disponível, mas terá acesso completo ao Discord"/>
    <div class="separator"></div>
    <StatusItems statusName="Definir status personalizado">
      <Emote class="icon-custom" size="20" slot="icon" />
    </StatusItems>
  </div>
</template>

<script>
  import StatusItems from './StatusItems'
  import Emote from 'vue-material-design-icons/EmoticonOutline'

  export default {
    components: {
      StatusItems,
      Emote
    },

    //Passar variavel: online, offline, etc
    methods: {
      handleChangeStatusOnline() {
        this.$emit('selected', 'online');
      },

      handleChangeStatusAbsent() {
        this.$emit('selected', 'absent');
      },

      handleChangeStatusNotDisturb() {
        this.$emit('selected', 'notDisturb');
      },

      handleChangeStatusInvisible() {
        this.$emit('selected', 'invisible');
      }
    }
  }

</script>

<style scoped lang="scss">
  .container {
    width: 220px;
    height: 282px;
    justify-content: space-between;
    display: flex;
    flex-direction: column;
    background: #18191c;
    position: relative;
    right: 7px;
    top: 80px;
    border-radius: 4px;
    overflow: hidden scroll;

    &::-webkit-scrollbar {
      display: none;
    }
  }

  .separator {
    border-bottom: solid 1px hsla(0,0%,100%,0.06);;
  }
</style>
