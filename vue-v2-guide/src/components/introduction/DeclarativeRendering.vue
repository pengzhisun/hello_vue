<template>
  <div>
    <div>
      <h3>Sample 01</h3>
      {{ sample_01.message }}
    </div>
    <div>
      <h3>Sample 02</h3>
      <span v-bind:title="sample_02.message">
        Hover your mouse over me for a few seconds
        to see my dynamically bound title!
      </span>
    </div>
  </div>
</template>

<script>
export default {
  metadata: {
    title: 'Declarative Rendering'
  },
  data() {
    return {
      sample_01: {
        message: 'Hello Vue!'
      },
      sample_02: {
        message: `You loaded this page on ${new Date().toLocaleString()}`
      }
    };
  },
  mounted() {
    document.$subComponent = this;
  }
};
</script>
