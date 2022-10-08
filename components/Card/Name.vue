<script setup lang="ts">

interface Prop{
    name: string;
    index: number;
}

defineProps<Prop>();
defineEmits(['remove']);
</script>

<template>
<div
            class="d-inline-flex  justify-content-center align-items-center gap-2 badge bg-primary px-3 py-2 mx-1"
        >
          {{ name }}
          <span 
          class="px-2 py-1 bg-danger text-white"
           style="border-radius: 50%"
           @click="$emit('remove',index)">x</span>
        </div>
</template>