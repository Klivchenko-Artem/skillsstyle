<template>
  <div :class="{'dark-mode': isDarkMode}" class="app">
    <appMenu
      v-for="(group, index) in groups"
      :key="index"
      :title="group.title"
      :items="group.items"
    />

    <button class="toggle-theme-button" @click="toggleTheme">Toggle Theme</button>
  
  </div>
</template>

<script>
import appMenu from './components/down/vue/appMenu.vue';

export default {
  components: {
    appMenu
  },
  data() {
    return {
      groups: [
        {
          title: 'Buff',
          items: [
            { title: 'Speed Bonus 30%', image: require('./components/down/img/speedapp.png'), description: 'Increases the hero TFR by 30%' },
            { title: 'Protection Bonus 60%', image: require('./components/down/img/defapp.png'), description: 'Increases the champion defense score by 60%' },
            {title: 'Attack Bonus 50%', image: require('./components/down/img/atkapp.png'), description: 'Increases the hero ATK by 50%' }
          ]
        },
        {
          title: 'Debuff',
          items: [
            {
              title: 'The speed penalty is 30%',
              image: require('./components/down/img/speeddown.png'),
              description: 'Reduces the speed of the champion by 30%.'
            },
            {
              title: 'The protection penalty is 60%',
              image: require('./components/down/img/defdown.png'),
              description: 'Reduces the champion defense by 60%.'
            },
            {
              title: 'The attack penalty is 50%',
              image: require('./components/down/img/atkdown.png'),
              description: 'Reduces the champion attack by 50%.'
            }
          ]
        }
      ],
      isDarkMode: false
    };
  },
  methods: {
    toggleTheme() {
      this.isDarkMode = !this.isDarkMode;
    }
  }
};
</script>

<style>
.app {
  max-width: 100%;
  min-height: 100vh;
  margin: 0 auto;
  padding: 20px;
  background-color: white;
  color: black;
  transition: background-color 1s ease, color 1s ease;
}

.dark-mode {
  background-color: #333;
  color: white;
}

.toggle-theme-button {
  display: block;
  margin: 50px auto;
  padding: 10px 20px;
  border: 2px solid black;
  background-color: white;
  color: black;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s ease, color 0.3s ease, border-color 0.3s ease;
}

.dark-mode .toggle-theme-button {
  background-color: #333;
  color: white;
  border-color: white;
}
</style>
