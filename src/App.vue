<template>
    <real-digital-form action="https://httpbin.org/post"
 method="POST">
 <real-digital-textfield name="name" validation="[a-z]+" />
 <real-digital-textfield name="phone" validation="[0-9]+" />
 <real-digital-textfield name="subject" />
 <real-digital-button>
 Send
 </real-digital-button>
 </real-digital-form>
</template>

<script>
import RealDigitalButton from './components/RealDigitalButton.vue';
import RealDigitalForm from './components/RealDigitalForm.vue';
import RealDigitalTextfield from './components/RealDigitalTextfieldd.vue';

export default {
  name: 'App',
  components: {
    RealDigitalForm,
    RealDigitalTextfield,
    RealDigitalButton,
  },
};
</script>

<style>
#app,
    RealDigitalButton {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
