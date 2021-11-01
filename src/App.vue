<template>
  <div class="flex flex-col mt-16 items-center">
    <h1 class="text-4xl px-8 py-16 mx-auto bg-green-400 rounded-xl text-center">{{ header }}</h1>
    <button class="bg-gray-600 mt-8 px-6 py-3 rounded-xl text-white uppercase" @click="toggleModal">Show Modal</button>
  </div>
  <div v-if="showModal">
    <modal @close="toggleModal" theme="dark">
      <h1 class="text-4xl">Modal Title</h1>
      <p class="text-xl">Modal Conent</p>
      <template v-slot:links>
        <div class="mt-6">
          <a class="border border-yellow-400 px-6 py-3 rounded-lg mr-5" href="#">Sign up</a>
          <a class="border border-green-400 px-6 py-3 rounded-lg" href="#">More Info</a>
        </div>
      </template>
    </modal>
  </div>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal,
  },
  data() {
    return {
      header: 'Demonstration of Modal by Vue.js',
      showModal: false,
      title: 'Modal Title',
      content: 'Modal content',
    }
  },

  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    },
  },
}
</script>
