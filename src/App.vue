<template>
  <header class="container flex flex-wrap px-4 max-w-md md:max-w-2xl mx-auto justify-center my-3">
    <img alt="Vue logo" class="max-w-xs" src="./assets/logo.svg"/>
    <div class="mt-5">
      <h1>Hello World!</h1>
      <HelloComponent msg="Richard Laurent" />
      <div :title="hoverHitung" class="the-Counter">The Counter : {{ hitung }}</div>

      <!-- Plus Buton -->
      <button type="button" class="btn-plus"
        @click="plusBtn"
      >Plus</button>

      <!-- Minus Button -->
      <button type="button" class="btn-minus"
        @click="minusBtn"
      >Minus</button>

      <!-- Reset Button -->
      <button type="button" class="btn-plus"
        @click="resetBtn"
        v-if="status"
      >Reset</button>

      <!-- Input v-model -->
      <div class="my-5 text-2xl font-semibold max-w-lg text-center mx-auto">{{ pesan }}</div>
      <input v-model="pesan" class="inputVModel" />
    </div>
  </header>
</template>

<script>
import HelloComponent from './components/HelloComponent.vue'

export default {
  name: 'App',
  components: {
    HelloComponent
  },
  data() {
    return {
      hitung: 0,
      hoverHitung: "Hitung Angka",
      pesan: "\"\"",
      status: false
    }
  },
  methods: {
    plusBtn() {
      if (this.hitung != 0) {
        this.status = true
        this.hitung++
      } else if (this.hitung == 0) {
        this.status = !this.status
        this.hitung++
      }
    },
    minusBtn() {
      if (this.hitung > 0) {
        this.status = true
        this.hitung--
      } else {
        this.status = false
        alert('Nilai tidak boleh minus')
      }
    },
    resetBtn() {
      if (this.hitung != 0) {
        this.status = true
        this.hitung = 0
      } else if (this.hitung == 0) {
        this.status = false
      }
    }
  },
}
</script>