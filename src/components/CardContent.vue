<template>
  <div>
      <p class="body m-2 p-3 text-gray-600">
        <slot name="text"> <button class="bg-yellow-500  text-gray-100 rounded font-bold m-2  hover:bg-red-400 px-2 py-1 focus:outline-none
        inline-flex align-middle text-md"> UNDO
    </button> </slot>       
      </p>
      <slot name="text"></slot>       
      
  </div>
</template>

<script>
export default {
  data: function() {
    return {
        flipped: false
    };
  },
  }
 
</script>

<style></style>
