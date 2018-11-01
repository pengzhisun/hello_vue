<template>
  <div>
    <div class="menu">
      <h3>Introduction</h3>
      <ul>
        <li v-for="info in componentInfos" :key="info.componentName">
          <a href="#" @click="menuItemClicked"
                      :data-component-name="info.componentName"
                      :data-component-title="info.componentTitle">
            {{ info.componentTitle }}
          </a>
        </li>
      </ul>
    </div>
    <div id="subComponent" :v-show="subComponentShown" class="sub-component">
      <h3>
        <a href="#" title="close" @click="subComponentTitleClicked">
          {{ subComponentTitle }}
        </a>
      </h3>
      <component :is="subComponentName" />
    </div>
  </div>
</template>

<script>
import DeclarativeRendering from './introduction/DeclarativeRendering.vue';
import ConditionalsLoops from './introduction/ConditionalsLoops.vue';
import HandlingUserInput from './introduction/HandlingUserInput.vue';
import ComposingComponents from './introduction/ComposingComponents.vue';

export default {
  components: {
    DeclarativeRendering,
    ConditionalsLoops,
    HandlingUserInput,
    ComposingComponents
  },
  data() {
    return {
      subComponentTitle: '',
      subComponentName: ''
    };
  },
  computed: {
    subComponentShown: function() {
      return !this.subComponentName;
    },
    componentInfos: function() {
      const infos = [];

      const components = this.$options.components;
      for (const componentName in components) {
        if (Object.prototype.hasOwnProperty.call(components, componentName)) {
          const component = components[componentName];

          infos.push({
            componentName,
            componentTitle: component.props.title
          });
        }
      }

      return infos;
    }
  },
  methods: {
    menuItemClicked: function(e) {
      const menuItem = e.target;
      this.subComponentTitle = menuItem.dataset.componentTitle;
      this.subComponentName = menuItem.dataset.componentName;
      e.preventDefault();
    },
    subComponentTitleClicked: function(e) {
      this.subComponentTitle = '';
      this.subComponentName = '';
      e.preventDefault();
    }
  },
  mounted() {
    document.$intro = this;
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #9db9ac;
}

.menu {
  float: left;
  width: 30%;
  min-width: 120px;
}

.sub-component {
  float: left;
  min-width: 600px;
}
</style>
