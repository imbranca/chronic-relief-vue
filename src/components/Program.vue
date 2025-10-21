<template>
  <div class="flex program__item w-full p-4 bg-white my-2 rounded-md flex-col" 
      :class="{ 'active': index === currentIndex }"
      :key="index"
      @click="handleTap(index, $event)"
      @touchend="handleTap(index, $event)"
      v-for="(week, index) in programWeeks">
      <!--Only for desktop-->
      <div class="program__header flex">
        <div class="program__icon">
        </div>
        <div class="program__information">
          <div class="program__title text-xl">{{ week.title }}</div>
          <div class="program__description text-base">{{ week.description }}</div>
        </div>
        <div class="program__icon-wrapper w-20 flex ml-auto">
          <ChevronRight v-if="index !== currentIndex" class="my-auto ml-auto"/>
          <ChevronDown v-else class="my-auto ml-auto"/>
        </div>
      </div>
      <div class="program__body mt-4">
          <div class="program__expanded" v-html="week.content">
        </div>
      </div>
  </div>
  <div class="flex program__item w-full p-4 bg-white my-2 rounded-md flex-col">
     <div class="program__title text-xl mt-2">Practical Exercises (All Weeks)</div>
     <div class="program__description text-base mt-2">Alongside the weekly lessons, you’ll find 42 practical exercises that support your body’s natural recovery processes:</div>
      <ul class="list-disc pl-4 mb-2 mt-2">
          <li>Breathing Exercises – Calm the nervous system</li>
          <li>Mobilization Exercises – Restore movement and balance</li>
          <li>Stretching Exercises – Release tension and improve flexibility</li>
          <li>Nerve Mobilization Exercises – Support neural recovery</li>
          <li>Releasing Neck Tension – Reduce headaches and stress</li>
          <li>Somatic Exercises – Strengthen mind-body awareness</li>
      </ul>
  </div>
</template>
<script setup>
  import {ChevronDown, ChevronRight} from 'lucide-vue-next';
  import {ref, defineProps} from 'vue';

  const props = defineProps({
    programWeeks: Array
  });

  const currentIndex = ref(null);
  const lastTouch = ref(0)

  function handleTap(index, event) {
    const now = Date.now()
    if (event.type === 'touchend') {
      lastTouch.value = now
      setCurrentIndex(index)
    } else if (event.type === 'click' && now - lastTouch.value > 500) {
      setCurrentIndex(index)
    }
  }

  function setCurrentIndex(index) {
    if (currentIndex.value != index) {
      currentIndex.value = index;
    } else {
      currentIndex.value = null;
    }
  }
</script>

<style lang="scss">
  div {
    touch-action: manipulation; /* Prevents double-tap zoom, helps trigger touch/click */
    -webkit-tap-highlight-color: transparent; /* Optional, removes blue flash */
  }

  .program__item {
    cursor: pointer;
    pointer-events: auto;
    touch-action: manipulation;
  }

  .program__item{
    border: solid 1px #e7e6e2;
  }
  .program__body {
    display: none;
  }
  .program__item.active .program__body{
    display: flex;
  }
  // .program__item.active .program__icon-wrapper{
  //    transform: rotate(90deg);
  // }
  .program__body p{
    margin-bottom: 10px;
  }
</style>