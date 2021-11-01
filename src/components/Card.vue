<template>
    <div class = "flip_container mt-10" @click="flip_card">
       <div class="flip w-80 relative">

    <transition name="front_beh" >
      <div 
        v-if="!flipped"
        key="front"
        class="front
        w-80 
        h-full 
        bg-green-200 
        shadow-xl 
        rounded-lg ">       
        <slot name="front"></slot>
      </div>
      <div
        v-if="flipped"
        key="back"
        class="back
        w-80 
        h-full 
        bg-blue-200 
        shadow-xl 
        rounded-lg" >       
        <slot name="back"></slot>
      </div>
      </transition>
      </div>
      </div>
</template>

<script>
export default {
  name: "Card",
  data: function () {
    return {
      flipped: false,
    };
    
  },methods:
    {
      flip_card()
      {
        this.flipped=!this.flipped
      }
    }
};
</script>

<style type='text/css' scoped>

.front_beh-enter-active,.front_beh-leave-active,.back_beh-enter-active,.back_beh-leave-active {
    -webkit-backface-visibility: hidden;
  -moz-backface-visibility: hidden;
  -o-backface-visibility: hidden;
  backface-visibility: hidden;
  -webkit-transition: 3s;
  -webkit-transform-style: preserve-3d;
  -moz-transition: 3s;
  -moz-transform-style: preserve-3d;
  -o-transition: 3s;
  -o-transform-style: preserve-3d;
  -ms-transition: 3s;
  -ms-transform-style: preserve-3d;
  transition: 3s;
  transform-style: preserve-3d;
  top: 0;
  left: 0;
}

.front_beh-enter{
    transform: rotateY(-180deg);
    opacity:1;
    
}
.front_beh-leave
{
  transform: rotateY(180deg);
  opacity: 0;
}

.front_beh-leave-active
{
  transform: rotateY(180deg);
  position:absolute;
  opacity: 1;
}

ασ
</style>