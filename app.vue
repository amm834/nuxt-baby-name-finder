<script setup lang="ts">
type Gender = 'Girl' | 'Boy';
type Popularity = 'Trendy' | 'Unique';
type LengthOfName = 'Long' | 'Short' | 'All';

const options = $ref<{
  gender: Gender,
  popularity: Popularity,
  length: LengthOfName
}>({
  gender: 'Girl',
  popularity: 'Unique',
  length: "Long"
});
</script>

<template>
  <div class="mt-4 container d-flex flex-column justify-content-center align-items-center">
    <h1>Baby Name Generator</h1>
    <p>Choose your options and click the "Find Name" button below</p>
    <div class="card px-5 py-3 border-0 shadow-sm w-100">
      <div class="mb-3">
        <h5 class="text-center">1) Choose a gender </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-outline-primary" :class="options.gender === 'Boy' && 'active'">Boy
          </button>
          <button type="button" class="btn btn-outline-primary" :class="options.gender === 'Unisex' && 'active'">
            Unisex
          </button>
          <button type="button" class="btn btn-outline-primary" :class="options.gender === 'Girl' && 'active'">Girl
          </button>
        </div>
      </div>
      <div class="mb-3">
        <h5 class="text-center"> 2) Choose the name's popularity </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-outline-primary" :class="options.popularity === 'Trendy' && 'active'">
            Trendy
          </button>
          <button type="button" class="btn btn-outline-primary" :class="options.popularity === 'Unique' && 'active'">
            Unique
          </button>
        </div>
      </div>
      <div class="mb-3">
        <h5 class="text-center">3) Choose the name's length </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-outline-primary" :class="options.length === 'Long' && 'active'">Long
          </button>
          <button type="button" class="btn btn-outline-primary" :class="options.length === 'All' && 'active'">All
          </button>
          <button type="button" class="btn btn-outline-primary" :class="options.length === 'Short' && 'active'">Short
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
@import "https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css";
</style>