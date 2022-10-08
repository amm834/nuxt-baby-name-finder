<template>
  <div>
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
      <!--        find names -->
      <div class="d-flex justify-content-center">
        <button
            class="btn btn-primary mt-4"
            @click="onGenerateNames"
        >Find Names
        </button>
      </div>

    </div>
  </div>
</template>
