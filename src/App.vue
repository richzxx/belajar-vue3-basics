<template>
  <header class="container flex flex-wrap px-4 max-w-md md:max-w-2xl mx-auto justify-center my-3">
    <img alt="Vue logo" class="max-w-xs" src="./assets/logo.svg"/>
    <div class="mt-5">
      <h1>Hello World!</h1>
      <hello-component msg="Richard Laurent" />
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

  <main class="container flex flex-col px-4 max-w-md md:max-w-xl mx-auto justify-center mt-10">

    <div class="rounded-2xl shadow-md border border-slate-200 px-16 py-16">
      <ol class="list-decimal">
        <li v-for="(todo, i) in todos" :key="todo.id">
          {{ todo.activity }} <span class="italic font-semibold">(index: {{i}})</span>
        </li>
      </ol>
    </div>

    <pengulangan-component 
      v-for="i in pengulanganComponent" 
      :key="i"
      :pengulangan="i"
    />

    <div class="mt-96 mx-auto">--- End Content ---</div>
  </main>
</template>

<script>
import HelloComponent from './components/HelloComponent.vue'
import PengulanganComponent from './components/PengulanganComponent.vue'

export default {
  name: 'App',
  components: {
    HelloComponent,
    PengulanganComponent
  },
  data() {
    return {
      hitung: 0,
      hoverHitung: "Hitung Angka",
      pesan: "\"\"",
      status: false,
      todos: [
        {id: 1, activity: 'Requirements'},
        {id: 2, activity: 'Design'},
        {id: 3, activity: 'Development'},
        {id: 4, activity: 'Testing'},
        {id: 5, activity: 'Deployment'},
        {id: 6, activity: 'Review'}
      ],
      pengulanganComponent: [
        'Richard',
        'Gio',
        'John',
        'Michael'
      ]
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
        this.status = !this.status
        this.hitung = 0
      } else if (this.hitung == 0) {
        this.status = false
      }
    }
  },
}
</script>