<script setup lang="ts">
import {Gender, Popularity, Length} from "~/data";
import {$ref} from "vue/macros";

interface OptionsState {
  gender: Gender,
  popularity: Popularity,
  length: Length
}

const options = reactive<OptionsState>({
  gender: Gender.GIRL,
  popularity: Popularity.UNIQUE,
  length: Length.LONG,
});

const selectedNames = $ref<string[]>([]);

</script>

<template>
  <div class="mt-4 container d-flex flex-column justify-content-center align-items-center">
    <h1>Baby Name Generator</h1>
    <p>Choose your options and click the "Find Name" button below</p>
    <div class="card px-5 py-3 border-0 shadow-sm w-100">
      <div class="mb-3">
        <h5 class="text-center">1) Choose a gender </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-outline-primary"
                  :class="options.gender === Gender.BOY && 'active'"
                  @click="options.gender = Gender.BOY"
          >Boy
          </button>
          <button type="button" class="btn btn-outline-primary"
                  :class="options.gender === Gender.UNISEX && 'active'"
                  @click="options.gender = Gender.UNISEX"
          >
            Unisex
          </button>
          <button type="button" class="btn btn-outline-primary"
                  :class="options.gender === Gender.GIRL && 'active'"
                  @click="options.gender = Gender.GIRL"
          >Girl
          </button>
        </div>
      </div>
      <div class="mb-3">
        <h5 class="text-center"> 2) Choose the name's popularity </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-outline-primary"
                  :class="options.popularity === Popularity.TRENDY && 'active'"
                  @click="options.popularity = Popularity.TRENDY"
          >
            Trendy
          </button>
          <button type="button" class="btn btn-outline-primary"
                  :class="options.popularity === Popularity.UNIQUE && 'active'"
                  @click="options.popularity = Popularity.UNIQUE"
          >
            Unique
          </button>
        </div>
      </div>
      <div class="mb-3">
        <h5 class="text-center">3) Choose the name's length </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-outline-primary"
                  :class="options.length === Length.LONG && 'active'"
                  @click="options.length = Length.LONG"
          >Long
          </button>
          <button type="button" class="btn btn-outline-primary"
                  :class="options.length === Length.ALL && 'active'"
                  @click="options.length = Length.ALL"
          >All
          </button>
          <button type="button" class="btn btn-outline-primary"
                  :class="options.length === Length.SHORT && 'active'"
                  @click="options.length = Length.SHORT"
          >Short
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
@import "https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css";
</style>