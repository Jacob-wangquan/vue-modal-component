<template>
  <div id="app">
    <button @click="showModal" type="button" class="btn">打开Modal</button>
    <modal v-show="isModalVisible" @close="closeModal">
      <div slot="header">
        <h3>对话框</h3>
        <button type="button" class="btn-close" @click="closeModal">X</button>
      </div>
      <div class="content" slot="body">
        <p>这里是body</p>
      </div>
      <div slot="footer" type="button" @click="closeModal" class="btn-green">提交</div>
    </modal>
  </div>
</template>

<script>
import Modal from './components/Modal.vue';
export default {
  name: 'app',
  components: {
    Modal
  },
  data () {
    return {
      isModalVisible: false
    }
  },

  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
