<script setup lang="ts">
import { $ref } from "vue/macros";
import { Gender, Length, names, Popularity } from "~/data";

export interface OptionsState {
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
const optionSections = [
  {
    title: '1) Choose a gender',
    category: 'gender',
    buttons: [Gender.BOY, Gender.GIRL, Gender.UNISEX]
  },
  {
    title: '2) Choose the name\'s popularity ',
    category: 'popularity',
    buttons: [Popularity.TRENDY, Popularity.UNIQUE]
  },
  {
    title: '3) Choose the name\'s length',
    category: 'length',
    buttons: [Length.SHORT, Length.LONG, Length.ALL]
  },
]

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

      <BaseOption
          v-for="section in optionSections"
          :key="section.toString()"
          :section="section"
          :options="options"
      />

<div>
<button class="btn btn-primary my-3"
@click="onGenerateNames"
>Find Names</button>
</div>
      <!--          names -->
      <div class="d-flex justify-content-center mt-4">
        <CardName 
        v-for="(name,index) in selectedNames"
        :key="index"
        :name="name"
          :index="index"
        @remove="selectedNames.splice(index,1)"
        />
      </div>
    </div>
  </div>
</template>

<style>
@import "https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css";
</style>