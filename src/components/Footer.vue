<template>
  <footer class="bg-[#415364]">
    <div class="container mx-auto pb-5">
      <div class="footer_link-container">
        <ul class="py-5 header__optionWrapper text-white is-active grid grid-cols-2">
          <li class="mt-2 text-base uppercase"> Home </li>
          <li class="mt-2 text-base uppercase"> Services </li>
          <li class="mt-2 text-base uppercase"> Program </li>
          <li class="mt-2 text-base uppercase"> Contact </li>
        </ul>
      </div>
      <div class="footer__icons flex gap-3">
        <Instagram :size="18" color="#ffffff"/>
        <Facebook :size="18" color="#ffffff"/>
      </div>
      <div class="footer__copyright mt-4">
        <p class="footer-copyright text-xs text-white">Copyrights © <span class="copyright-year">2025</span>&nbsp;All Rights Reserved by Pain Canada. <br>All trademarks, trade names or logos mentioned or used herein are the property of their respective owners.</p>
    </div>
    </div>

  </footer>
</template>

<script setup>
  import { Facebook, Instagram } from 'lucide-vue-next';

</script>

<style scoped lang="scss">
  .container{
    max-width: 85%;
  }
</style>