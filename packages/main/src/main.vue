<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps(['name'])

const emit = defineEmits([
  'go',
  'update:name'
])

function go(){
  emit('go')
}

const name = computed({
  get() {
    return props.name
  },
  set(value) {
    emit('update:name', value)
  }
})

</script>

<template>
  <div>
    <div class="text-4xl inline-block i-carbon-wave-direction" />

    <p>Vitem</p>

    <p>
      <em class="opacity-75 text-sm">
        Opinionated Vue Vite Starter Template
      </em>
    </p>

    <div class="py-4" />

    <input
      v-model="name"
      placeholder="What's your name?"
      class="px-4 py-2 w-64 text-center bg-transparent outline-none border rounded border-solid border-gray-200 dark:border-gray-700 active:outline-none"
      autoComplete="false"
      type="text"
    >

    <div>
      <button @click="go" :disabled="props.name.length <= 0" class="m-3 text-sm btn">
        Go
      </button>
    </div>
  </div>
</template>
