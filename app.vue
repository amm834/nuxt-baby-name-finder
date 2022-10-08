<template>
  <div class="mt-4 container d-flex flex-column justify-content-center align-items-center">
    <h1>Baby Name Generator</h1>
    <p>Choose your options and click the "Find Name" button below</p>
    <div class="card px-5 py-3 border-0 shadow-sm w-100">
      <div class="mb-3">
        <h5 class="text-center">1) Choose a gender </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-primary">Boy</button>
          <button type="button" class="btn btn-primary">Unsex</button>
          <button type="button" class="btn btn-primary">Girl</button>
        </div>
      </div>
      <div class="mb-3">
        <h5 class="text-center"> 2) Choose the name's popularity </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-primary">Trendy</button>
          <button type="button" class="btn btn-primary">Unique</button>
        </div>
      </div>
      <div class="mb-3">
        <h5 class="text-center">3) Choose the name's length </h5>
        <div class="btn-group mt-3 d-flex justify-content-center" role="group" aria-label="Basic example">
          <button type="button" class="btn btn-primary">Long</button>
          <button type="button" class="btn btn-primary">All</button>
          <button type="button" class="btn btn-primary">Short</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
@import "https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css";
</style>