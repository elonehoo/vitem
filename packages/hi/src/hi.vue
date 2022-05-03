<script setup lang="ts">
const props = defineProps<{ name: string }>()

const emit = defineEmits([
  'back'
])

function back(){
  emit('back')
}
</script>

<template>
  <div>
    <div class="text-4xl inline-block i-carbon-construction" />

    <p>Hi, {{ props.name }}</p>

    <p class="text-sm opacity-50">
      <em>Dynamic route!</em>
    </p>

    <div>
      <button
        class="text-sm mt-8 m-3 btn"
        @click="back"
      >
        Back
      </button>
    </div>
  </div>
</template>
