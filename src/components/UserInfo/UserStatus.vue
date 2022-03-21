<template>
  <div class="container">
    <StatusItems online statusName="Disponível"/>
    <div class="separator"></div>
    <StatusItems absent statusName="Ausente"/>
    <StatusItems notDisturb statusName="Não pertubar" description="Você não irá mais receber notificações na área de trabalho"/>
    <StatusItems invisible statusName="Invisível" description="Você não aparecerá como disponível, mas terá acesso completo ao Discord"/>
    <div class="separator"></div>
    <StatusItems custom statusName="Definir status personalizado"/>
  </div>
</template>

<script>
  import StatusItems from './StatusItems'

  export default {
    components: {
      StatusItems
    }
  }

</script>

<style scoped lang="scss">
  .container {
    width: 220px;
    height: 282px;
    max-height: 100vh;
    display: flex;
    flex-direction: column;
    position: relative;
    background: #18191c;
    padding: 6px 8px 6px 8px;
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
