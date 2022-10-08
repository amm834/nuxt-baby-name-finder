<script setup lang="ts">import { OptionsState } from '~/app.vue';
import { Gender, Length, Popularity } from '../data';

interface Props {
  options: OptionsState,
  section: {
    title: string,
    category: string,
    buttons: Gender[] | Popularity[] | Length[]
  }
}

defineProps<Props>()
</script>

<template>
  <div>
    <div class="mb-3">
      <h5 class="text-center">{{ section.title }}</h5>
      <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
        <button type="button"
         class="btn btn-outline-primary"
                v-for="button in section.buttons"
                :class="options[section.category] === button && 'active'"
                @click="options[section.category] = button"
                :key="button.toString()"
        >
          {{ button }}
        </button>
      </div>
    </div>
  </div>
</template>
