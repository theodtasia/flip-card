<template>
  <div
    id="app"
      class="grid grid-cols-1 gap2 justify-items-center text-center overflow-hidden">
    <card v-for="card in cards" :key="card.id">
      <template slot="front">{{ card.front }}</template>
      <template slot="back">{{ card.back }}</template>
    </card>
  </div>
</template>

<script>
import Card from "./components/Card.vue";
export default {
  name: "App",
  components: {
    Card,
  },
  data() {
    return {
      cards: [
        {
          id:0,
          front: " Welcome Rapidly build modern websites without ever leaving your HTML.",
          back:"Welcome Rapidly build modern websites without ever leaving your HTML.",
        },
        {
          id:1,
          front: " AAAAAAAWelcome Rapidly build modern websites without ever leaving your HTML.",
          back:"For example, mt-6 would add 1.5rem of marginsssssssssss to the top of an element, mr-4 w ould add 1rem of margin to the right of an elemor example, mt-6 would at-6 would add 1.5rem of margin to the top of an element, mr-4 w ould add 1rem of margin to the right of an elemor example, mt-6 would add 1.5rem of margin to the top of an element, mr-4 would add 1rem of margin to the right of an element, mb-8 would add 2rem of margin to the bottom of an element, and ml-2 would add 0.5rem of margin to the left of an element.",
        },
        {
          id:2,
          front: " AAAAAAAWelcome Rapidly build modern websites without ever leaving your HTML.",
          back:"For example, mt-6 would add 1.5rem of margin to the top of an element, mr-4 would add 1re;;;;;;;;;;;;;;;;;;;m of margin to the right of an element, mb-8 would add 2rem of margin to the bottom of an element, and ml-2 would add 0.5rem of margin to the left of an element.",
        },
        
      ],
    };
  },
};
</script>

