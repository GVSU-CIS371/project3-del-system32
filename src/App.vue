<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul>
      <li>
        <label>
          Temperature:
        </label>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
      <li>
        <label>
          Creamer:
        </label>
        <template v-for="creamer in creamers" :key="creamer">
          <label>
              <input
                type="radio"
                name="creamer"
                :id="`r${creamer}`"
                :value="creamer"
                v-model="currentCreamer"
              />
              {{ creamer }}
          </label>
        </template>
      </li>
      <li>
        <label>
          Syrup:
        </label>
        <template v-for="syrup in syrups" :key="syrup">
          <label>
              <input
                type="radio"
                name="syrup"
                :id="`r${syrup}`"
                :value="syrup"
                v-model="currentSyrup"
              />
              {{ syrup }}
          </label>
        </template>
      </li>
      <li>
        <label>
          Base Beverage:
        </label>
        <template v-for="base in bases" :key="base">
          <label>
              <input
                type="radio"
                name="base"
                :id="`r${base}`"
                :value="base"
                v-model="currentBase"
              />
              {{ base }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
// Define reactive data
const temps = ref(["Hot", "Cold"]);
const currentTemp = ref("Hot");


import Creamer from "./components/Creamer.vue"

const creamers = ref(["None", "Milk", "Cream", "Half & Half"]);
const currentCreamer = ref("Half & Half");

import Syrup from "./components/Syrup.vue"

const syrups = ref(["None", "Vanilla", "Caramel", "Hazelnut"]);
const currentSyrup = ref("Vanilla");

import Base from "./components/Base.vue"

const bases = ref(["Coffee", "Green Tea", "Black Tea"]);
const currentBase = ref("Coffee");
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
