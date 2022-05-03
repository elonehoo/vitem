<script setup lang="ts">
import Main from '@vitem/main'
import { useRouter } from 'vue-router'

const router = useRouter()

const name:string = $ref('')

function go(){
  if (name.length > 0)
    router.push(`/hi/${encodeURIComponent(name)}`)
}
</script>

<template>
<Main v-model:name="name" @go="go" />
</template>
