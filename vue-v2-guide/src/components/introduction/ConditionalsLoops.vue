<template>
  <div>
    <div>
      <h3>Sample 01</h3>
      <span v-if="sample_01.seen">
        Now you see me
      </span>
      <pre>document.$subComponent.$data.sample_01.seen = {{!sample_01.seen}}</pre>
    </div>
    <div>
      <h3>Sample 02</h3>
      <ol>
        <li v-for="todo in sample_02.todos" :key="todo.text">
          {{ todo.text }}
        </li>
      </ol>
    </div>
  </div>
</template>

<script>
export default {
  metadata: {
    title: 'Conditional And Loops'
  },
  data() {
    return {
      sample_01: {
        seen: true
      },
      sample_02: {
        todos: [
          { text: 'Learn JavaScript' },
          { text: 'Learn Vue' },
          { text: 'Build something awesome' }
        ]
      }
    };
  },
  mounted() {
    document.$subComponent = this;
  }
};
</script>

