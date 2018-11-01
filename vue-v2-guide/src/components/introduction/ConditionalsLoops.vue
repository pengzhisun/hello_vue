<template>
  <div>
    <div>
      <h3>Sample 01</h3>
      <span v-if="sample_01.seen">
        Now you see me
      </span>
      <pre>document.$subComponent.$data.sample_01.seen = {{!sample_01.seen}}</pre>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: "Conditional And Loops"
  },
  data() {
    return {
      sample_01: {
        seen: true
      }
    };
  },
  mounted() {
    document.$subComponent = this;
  }
};
</script>

