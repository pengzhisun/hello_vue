<template>
  <div>
    <div>
      <h3>Sample 01</h3>
      <p>{{ sample_01.message }}</p>
      <button v-on:click="reverseMessage">Reverse Message</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: 'Handling User Input'
  },
  data() {
    return {
      sample_01: {
        message: 'Hello Vue.js!'
      }
    };
  },
  methods: {
    reverseMessage: function () {
      this.sample_01.message = this.sample_01.message.split('').reverse().join('');
    }
  },
  mounted() {
    document.$subComponent = this;
  }
};
</script>
