<template>
  <div class="down">
    <div class="header" @click="toggle">
      <span>{{ title }}</span>
      <button>{{ isOpen ? '-' : '+' }}</button>
    </div>
    <div v-if="isOpen" class="content">
      <appList
        v-for="(item, index) in items"
        :key="index"
        :title="item.title"
        :image="item.image"
        :description="item.description"
      />
    </div>
  </div>
</template>

<script>
import appList from './appList.vue';

export default {
  components: {
    appList
  },
  props: {
    title: String,
    items: Array
  },
  data() {
    return {
      isOpen: false
    };
  },
  methods: {
    toggle() {
      this.isOpen = !this.isOpen;
    }
  }
};
</script>

<style scoped>
.down {
    margin: 20px 0;
    border: 1px solid #ccc;
    padding: 10px;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    padding: 10px;
}

.content {
    padding: 10px 0;
}
</style>