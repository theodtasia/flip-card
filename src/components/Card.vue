<template>

  <div v-bind:class="flipped ? 'flip-container flipped': 'flip-container'" @click="flipped = !flipped">
    <div class="flip w-80 mt-10 relative">
      <div class="front 
       bg-yellow-300 
       shadow-2xl
       rounded-xl 
       w-80">
        <slot name="front"></slot>
      </div>
      <div class="back 
      bg-blue-300 
       shadow-2xl
       rounded-xl 
       w-80">
        <slot name="back"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FlipCard',
  data: function() {
    return {
        flipped: false
    };
  }
};
</script>

<style type='text/css' scoped>

.flip-container 
{
  -webkit-perspective: 1000;
  -moz-perspective: 1000;
  -o-perspective: 1000;
  perspective: 1000;
  position:relative;
}

.flip {
  -moz-transform: perspective(1000px);
  -moz-transform-style: preserve-3d;
  min-height: 200px;
}
.front,
.back {
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
  width: 100%;
  min-height: 100px;
}
.back {
  -webkit-transform: rotateY(-180deg);
  -moz-transform: rotateY(-180deg);
  -o-transform: rotateY(-180deg);
  -ms-transform: rotateY(-180deg);
  transform: rotateY(-180deg);
  position: absolute;
  width: 100%;

}
.flip-container.flipped .back {
  -webkit-transform: rotateY(0deg);
  -moz-transform: rotateY(0deg);
  -o-transform: rotateY(0deg);
  -ms-transform: rotateY(0deg);
  transform: rotateY(0deg);
  

}
.flip-container.flipped .front {
  -webkit-transform: rotateY(180deg);
  -moz-transform: rotateY(180deg);
  -o-transform: rotateY(180deg);
  -ms-transform: rotateY(180deg);
  transform: rotateY(180deg);
}
.front {
  z-index: 2;
}
</style>