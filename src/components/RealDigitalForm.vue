<template>
  <form :action="action" :method="method" @submit="onSubmit">
    <slot> </slot>
  </form>
</template>

<script>
export default {
  name: 'RealDigitalForm',
  props: {
    action: String,
    method: String,
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      const data = {};
      // eslint-disable-next-line no-plusplus
      for (let index = 0; index < e.target.length; index++) {
        if (e.target[index].localName === 'input') {
          data[e.target[index].name] = e.target[index].value;
        }
      }
      fetch(e.target.action, {
        method: e.target.method,
        body: JSON.stringify(data),
      }).then((response) => response.json()).then((response) => {
        console.log('submitted', response);
      });
      console.log(data);
    },
  },
};
</script>
