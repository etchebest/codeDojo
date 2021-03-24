<template>
  <div class="content" v-show="cModal">
    <div class="modal">
      <button @click="fecharModal">Fechar</button>
      <slot name="header"> </slot>
      <slot name="content"> </slot>
      <slot name="footer"> </slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",

  data() {
    return {
      modal: false,
    };
  },
  props: {
    show: Boolean,
  },
  computed: {
    cModal() {
      return this.modal;
    },
  },
  methods: {
    abrirModal() {
      this.modal = true;
    },
    fecharModal() {
      this.modal = false;
    },
  },
};
</script>

<style lang="scss" >
.content {
  position: absolute;
  display: flex;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.1);
  width: 100vw;
  height: 100vh;
  .modal {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    background-color: #ccc;
    width: 80vh;
    margin: auto;
    border-radius: 10px;
    z-index: 99999;
  }
}
</style>
