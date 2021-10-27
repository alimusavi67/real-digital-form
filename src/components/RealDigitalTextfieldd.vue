<template>
<div>
  <label for="id">{{name}}: </label>
  <input :id="name" :name="name" v-on:change="signalChange" :pattern="validation">
    <p v-if="hasError">invalid data!</p>
</div>
</template>

<script>
export default {
  name: 'RealDigitalTextfield',
  props: {
    name: String,
    validation: String,
  },
  data() {
    return {
      hasError: false,
    };
  },
  methods: {
    signalChange(evt) {
      const rule = new RegExp(this.validation);
      if (rule.test(evt.target.value)) {
        this.hasError = false;
      } else {
        this.hasError = true;
      }
    },
  },
};
</script>
