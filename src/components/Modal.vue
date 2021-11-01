<template>
  <div class="fixed top-0 bg-gray-900 bg-opacity-95 flex h-screen w-full" @click.self="closeModal">
    <div :class="{dark: theme === 'dark'}" class="bg-gray-200 m-auto text-black w-96 h-96 rounded-lg flex flex-col justify-center items-center">
      <h1 class="text-4xl">{{ title }}</h1>
      <p class="text-xl">{{ content }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: ['title', 'content', 'theme'],
  methods: {
    closeModal() {
      this.$emit('close')
    },
  },
}
</script>
