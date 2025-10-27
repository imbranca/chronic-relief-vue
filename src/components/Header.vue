<template>
  <nav class="w-full bg-white flex justify-between">
    <div class="logo-wrapper mt-[-5px]">
     <img src="@/assets/images/kopf-logo.png" class="w-18 h-18"/>
    </div>
      <img v-on:click="showMenuMobile = !showMenuMobile" class="header__icon" alt="..." src="@/assets/icons/burger.svg" />
  </nav>
  <div 
  :class="showMenuMobile? 'is-active' : 'is-hidden'"
   class="header__options p-4 h-screen fixed top-0 right-0 z-10000">
    <X v-on:click="showMenuMobile = !showMenuMobile" class="ml-auto"/>
      <ul class="mt-30 header__optionWrapper"  :class="showMenuMobile? 'is-active' : 'is-hidden'">
        <li class="mt-7 text-xl font-medium">
          Home
        </li>
        <li class="mt-7 text-xl font-medium">
          Services
        </li>
        <li class="mt-7 text-xl font-medium">
          Program
        </li>
        <li class="mt-7 text-xl font-medium">
          Contact
        </li>
        <li class="mt-7">
           <button class="relative text-xl px-4 py-2 font-bold hero__btn">
            Free Session
          </button>
        </li>
      </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { X } from 'lucide-vue-next';

  const showMenuMobile = ref(false);

</script>

<style lang="scss">
  .header__options{

  transition: transform 0.5s ease-in-out;
  transform-style: preserve-3d;
    width: 80%;
    background-color: #fffaf8;
    // background-image: url('@/assets/images/kopf-logo.png');
    // background-size: contain;
    // background-repeat: no-repeat;
    // background-position: right 10% top 10%;
    &.is-hidden{
    transform: translate3d(101%, 0px, 0px) scale3d(1, 1, 1) rotateX(0deg) rotateY(0deg) rotateZ(0deg) skew(0deg, 0deg);
    }
    &.is-active{
      transform: translate3d(0%, 0px, 0px) scale3d(1, 1, 1) rotateX(0deg) rotateY(0deg) rotateZ(0deg) skew(0deg, 0deg);
    }
  }

  .header__optionWrapper{
  transition: transform 0.70s ease-in-out;
   transform-style: preserve-3d;
    &.is-hidden{
    transform: translate3d(100%, 0px, 0px) scale3d(1, 1, 1) rotateX(0deg) rotateY(0deg) rotateZ(0deg) skew(0deg, 0deg);
    }
    &.is-active{
      transform: translate3d(0%, 0px, 0px) scale3d(1, 1, 1) rotateX(0deg) rotateY(0deg) rotateZ(0deg) skew(0deg, 0deg);
    }
  }


  nav{
    height: 60px;
  }
  .header__icon {
    width: 50px;
  }

  .hero__btn{
    border: solid 2px black;
    color: black;
  }
</style>