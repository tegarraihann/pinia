<template>
  <h1>Menggunakan Store</h1>
  <p>Akses count: {{ todoStore.count }}</p>
  <p>Akses doubleCount : {{ todoStore.doubleCount }}</p>
  <button @click="todoStore.increment">+</button><br /><br />

  <h1>Tanpa Store</h1>
  <p>Akses count tanpa store: {{ count }}</p>
  <button @click="increment">+</button>
</template>

<script>
import { useTodoStore } from '../stores/todoStore'
import { ref } from 'vue'
 export default {
  setup() {
      const count = ref(0)
      const todoStore = useTodoStore()

      return { todoStore, count }
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