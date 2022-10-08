<script setup lang="ts">
import {Gender, Length, names, Popularity} from "~/data";
import {$ref} from "vue/macros";

interface OptionsState {
  gender: Gender,
  popularity: Popularity,
  length: Length
}

const options = $ref<OptionsState>({
  gender: Gender.GIRL,
  popularity: Popularity.UNIQUE,
  length: Length.LONG,
});

let selectedNames = $ref<string[]>([]);

const onGenerateNames = () => {
  const filteredNames = names.filter(name => name.gender === options.gender)
      .filter(name => name.popularity === options.popularity)
      .filter(name => {
        if (Length.ALL) return true;
        else return name.length === options.length;
      })
  selectedNames = filteredNames.map(name => name.name);
}
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
        <div class="d-flex justify-content-center">
          <button
              class="btn btn-primary mt-4"
              @click="onGenerateNames"
          >Generate Names
          </button>
        </div>
        <!--          names -->
        <div class="d-flex justify-content-center mt-4">
          <div
              class="d-inline-flex  justify-content-center align-items-center gap-2 badge bg-primary px-3 py-2 mx-1"
              v-for="(name,idx) in selectedNames"
              :key="idx"
          >
            {{ name }}
            <span class="px-2 py-1 bg-danger text-white" style="border-radius: 50%">x</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
@import "https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css";
</style>