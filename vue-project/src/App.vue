<script setup>
// import HelloWorld from './components/HelloWorld.vue'
// import TheWelcome from './components/TheWelcome.vue'


// =======================================
// SCSSTry DOME start
import SCSSTry from './components/SCSSTry.vue'
// SCSSTry DOME end
// =======================================


// =======================================
// Skeleton start
import Skeleton from './components/Skeleton.vue'
// Skeleton end
// =======================================

// =======================================
// ProvideTest start
import { provide } from 'vue'
import ProvideTest from './components/ProvideTest.vue'
provide('user', [{
  id: 1,
  name: 'amy',
  sex: '2'
}, {
  id: 2,
  name: 'tommy',
  sex: '1'
}])
// ProvideTest end
// =======================================


// =======================================
// ProvideTest_readOnly start
// import { ref, provide } from 'vue'
import { readonly } from 'vue'
import ProvideTest_readOnly from './components/ProvideTest_readOnly.vue'
const date = readonly(ref([{
    id: 1,
    name: 'amy',
    sex: '2'
}, {
    id: 2,
    name: 'tommy',
    sex: '1'
}]))
provide('user', date)
// ProvideTest_readOnly end
// =======================================


// =======================================
// one way data flow DOME start
import { ref } from "vue"
import Menu from './components/Menu.vue'
import Content from './components/Content.vue'

const isOpen = ref(false)
const toggleMenuOpen = () => {
  isOpen.value = !isOpen.value
}
// one way data flow DOME end
// =======================================



</script>

<template>
  <!-- <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
  </main> -->



  <!-- one way data flow DOME start -->
  <Menu :isOpen="isOpen" :toggleMenuOpen="toggleMenuOpen"></Menu>
  <Content :isOpen="isOpen" :toggleMenuOpen="toggleMenuOpen"></Content>
  <!-- one way data flow DOME end -->


  <!-- SCSSTry DOME start -->
  <SCSSTry />
  <!-- SCSSTry DOME start -->


  <!-- Skeleton start -->
  <Skeleton />
  <!-- Skeleton end -->


  <!-- ProvideTest start -->
  <ProvideTest />
  <!-- ProvideTest end -->


  <!-- ProvideTest_readOnly start -->
  <ProvideTest_readOnly />
  <!-- ProvideTest_readOnly end -->

</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
