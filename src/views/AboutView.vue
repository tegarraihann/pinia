<template>
  <h1>Menggunakan Store</h1>
  <p>Akses count: {{ countStore.count }}</p>
  <p>Akses doubleCount : {{ countStore.doubleCount }}</p>
  <button @click="countStore.increment">+</button><br /><br />

  <h1>Tanpa Store</h1>
  <p>Akses count tanpa store: {{ count }}</p>
  <button @click="increment">+</button>
</template>

<script>
import { useCountStore } from '../stores/countStore'
import { ref } from 'vue'
 export default {
  setup() {
      const count = ref(0)
      const countStore = useCountStore()

      return { countStore, count }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>

<!-- <script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script> -->