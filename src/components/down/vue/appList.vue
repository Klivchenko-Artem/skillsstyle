<template>
  <div class="inner-down">
    <div class="header" @click="toggle">
      <span>{{ title }}</span>
      <button>{{ isOpen ? '-' : '+' }}</button>
    </div>
    <div v-if="isOpen" class="content">
      <img :src="image" alt="Image" />
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    image: String,
    description: String
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
.inner-down {
    margin: 10px 0;
    border: 1px solid #ccc;
    padding: 10px;
}

.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    background-color: #f7f7f7;
    padding: 10px;
}

.content {
    display: flex;
    align-items: center;
    padding-top: 10px;
}

img {
    max-width: 100px;
    max-height: 100px;
    margin-right: 20px;
}

p {
    margin: 0;
}
</style>