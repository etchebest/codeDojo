<template>
  <div id="app">
    <Modal ref="myModal">
      <template slot="header">
        <h1>Modal</h1>
      </template>
      <template slot="content">
        <p>
          Você está prestes a marcar como concluída a AVD, deseja continuar?
        </p>
      </template>
      <template slot="footer">
        <button @click="confirmar()">Confirmar</button>
      </template>
    </Modal>
    <button @click="show()">Open modal</button>
  </div>
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",

  components: {
    Modal,
  },
  methods: {
    show() {
      this.$refs.myModal.abrirModal();
    },
    confirmar() {
      this.$refs.myModal.fecharModal();
      alert("Confirmado!");
    },
  },
};
</script>

<style lang="scss">
#app {
}
</style>



<!--
// Props

// <modal>
//   <template slot="header">
//     conteudo
//   </template>
//   <template slot="content">
//     conteudo
//   </template>
//   <template slot="fotter">
//     botao
//   </template>
// </modal>



Modal
<div>
  <slot name="header">
    conteudo template
  </slot>
</div> -->


// Slots

// - Modal -
// Header
// Conteudo
// Footer(Botões)
