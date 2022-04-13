<template>
  <div>
    <nav>
      <router-link :to="{ name: 'home' }">Home</router-link> |
      <router-link :to="{ name: 'work' }">Work</router-link> |
      <router-link :to="{ name: 'about' }">About</router-link> |
      <router-link :to="{ name: 'contact' }">Contact</router-link>
    </nav>
    <router-view v-slot="{ Component }">
      <transition name="route" mode="out-in">
        <component :is="Component"></component>
      </transition>
    </router-view>
  </div>
</template>

<script>
export default {
  setup() {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

/* Route transitions */

.route-enter-from {
  opacity: 0;
  transform: translateX(100px);
}

.route-leave-to {
  opacity: 0;
  transform: translateX(-100px);
}

.route-enter-active,
.route-leave-active {
  transition: all 1s ease-in-out;
  /* animation: route 0.5s ease-in-out; */
}

/* @keyframes route {
  0% {
    opacity: 0;
    transform: translateX(100px);
  }
  100% {
    opacity: 1;
    transform: translateX(-100px);
  }
} */
</style>
