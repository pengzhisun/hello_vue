<template>
  <div>
    <div>
      <h3>Sample 01</h3>
      <ol>
        <TodoItem01 />
      </ol>
    </div>
    <div>
      <h3>Sample 02</h3>
      <ol>
        <TodoItem02 v-for='item in sample_02.groceryList'
                    v-bind:todo='item'
                    v-bind:key='item.id'>
        </TodoItem02>
      </ol>
    </div>
  </div>
</template>

<script>
import TodoItem01 from './ComposingComponents/TodoItem01.vue';
import TodoItem02 from './ComposingComponents/TodoItem02.vue';

export default {
  metadata: {
    title: 'Composing with Components'
  },
  components: {
    TodoItem01,
    TodoItem02
  },
  data() {
    return {
      sample_02: {
        groceryList: [
          {
            id: 0,
            text: 'Vegetables'
          },
          {
            id: 1,
            text: 'Cheese'
          },
          {
            id: 2,
            text: 'Whatever else humans are supposed to eat'
          }
        ]
      }
    };
  },
  mounted() {
    document.$subComponent = this;
  }
};
</script>
