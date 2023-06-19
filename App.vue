<template>
  <input
  type="color"
  v-model="myColor"
  @input="onColorChange"
  />
  <a-config-provider>
    <a-button type="primary">Primary Button</a-button>
    <a-button type="primary" danger>Danger</a-button>
    <a-alert message="Success Text" type="success" />
  </a-config-provider>
</template>

<script>
import { ConfigProvider } from 'ant-design-vue';
export default {
  name: "App",
  data() {
    return {
      myColor: '#1890ff'
    }
  },
  methods: {
    onColorChange (event) {
      console.log(event)
      ConfigProvider.config({
        theme: {
          primaryColor: event.target.value,
          successColor: event.target.value,
          errorColor: event.target.value
        },
      });
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
