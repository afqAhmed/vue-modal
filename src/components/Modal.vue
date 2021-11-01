<template>
  <div class="fixed top-0 bg-gray-900 bg-opacity-95 flex h-screen w-full" @click.self="closeModal">
    <div :class="{ dark: theme === 'dark' }" class="bg-gray-200 m-auto text-black w-96 h-96 rounded-lg flex flex-col justify-center items-center">
      <slot></slot>
      <div>
        <slot name="links">
          <div class="mt-6">
            <!-- Default name slot -->
            <a class="border border-red-600 px-6 py-3 rounded-lg" href="#">Default</a>
          </div>
        </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: ['theme'],
  methods: {
    closeModal() {
      this.$emit('close')
    },
  },
}
</script>
