<script setup lang="ts">
import Hi from '@vitem/hi'
import { useRouter } from 'vue-router'
const props = defineProps<{ name: string }>()
const router = useRouter()

function back(){
  router.back()
}
</script>

<template>
<Hi :name="props.name" @back="back"/>
</template>
