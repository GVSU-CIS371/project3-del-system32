<template>
  <div class="syrup" :style="{'background-color': syrupColor, 'display': visible}"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
type Prop = {
  name: string;
};
type Syrup = {
  name: string;
  color: string;
};
const Syrups: Syrup[] = [
  {
    name: "Vanilla",
    color: "#FFEFD5",
  },
  {
    name: "Caramel",
    color: "#DAA520",
  },
  {
    name: "Hazelnut",
    color: "#6B4423",
  },
];


const props = defineProps<Prop>();

const syrupColor = computed(() => {
  if (props.name !== "None") {
    const base = Syrups.find(i => i.name === props.name);
    return base ? base.color : '';
  }
});

const visible = computed (() => {
  if (props.name == "None"){
    return "none";
  }
})

</script>
<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
