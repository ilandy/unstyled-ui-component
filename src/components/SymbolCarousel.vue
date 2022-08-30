<script setup>
  import { computed } from 'vue';
import { ref }  from 'vue'
  
  const i = ref(0)
  const transitionOffset = computed(() => {
    console.log(i.value)
    return { transform: `translateX(calc(${i.value} * (100 - (100 / 3 / 2)) / 3 * 1%))` }
  })
</script>

<template>
  <div class="uns-carousel">
    <div class="uns-carousel__wrap">
      <div
        class="uns-carousel__track"
        :style="transitionOffset"
      >
        <div class="uns-carousel-item">
          123
        </div>
        <div class="uns-carousel-item">
          456
        </div>
        <div class="uns-carousel-item">
          789
        </div>
        <div class="uns-carousel-item">
          234
        </div>
        <div class="uns-carousel-item">
          567
        </div>
        <div class="uns-carousel-item">
          567
        </div>
        <div class="uns-carousel-item">
          567
        </div>
        <div class="uns-carousel-item">
          567
        </div>
        <div class="uns-carousel-item">
          567
        </div>
        <div class="uns-carousel-item">
          567
        </div>
      </div>
      <div class="uns-carousel__controls">
        <button
          class="uns-carousel__control"
          @click="i++"
        >
          P
        </button>
        <button
          class="uns-carousel__control"
          @click="i--"
        >
          N
        </button>
      </div>
    </div>
    
    <div class="uns-carousel__indicators">
      <button class="uns-carousel__indicator">
        1
      </button>
      <button class="uns-carousel__indicator">
        2
      </button>
      <button class="uns-carousel__indicator">
        3
      </button>
      <button class="uns-carousel__indicator">
        4
      </button>
      <button class="uns-carousel__indicator">
        5
      </button>
    </div>
  </div>
</template>

<style scoped lang="scss">
.uns-carousel {
  --carousel-align: left;
  --indicator-align: center;
  --transition-duration:.4s;
  --item-size: calc((100 - (100 / 3 / 2)) / 3 * 1%); 
  
  overflow: hidden;
  width: 100%;

  &__wrap {
    position: relative;
    width: 100%;
  }
  &__track {
    transition: transform var(--transition-duration);
    display: flex;
    justify-content: var(--carousel-align);
  }

  &__controls {
    box-sizing: border-box;
    position: absolute;
    top: 50%;
    width: 100%;
    padding-left: 8px;
    padding-right: 8px;
    display: flex;
    justify-content: space-between;
    transform: translateY(-50%);
  }

  &__indicators {
    display: flex;
    justify-content: var(--indicator-align);
    padding-top: 8px;
  }

  &__indicator{
    &:not(:last-child) {
      margin-right: 8px;
    }
  }
  
  &-item {
    flex:  var(--item-size) 0 0; /* item 寬度控制 */
    height: 200px;
    background-color: #f00;
    font-size: 90px;
    display: flex;
    place-items: center;
    justify-content: center;
  }
}
</style>
    