<template>
<div>
  <Header />
  <PrimeiroComponente />
  <LifeCycle />
  <Pessoa :email="email" />
</div>
</template>

<script>
import PrimeiroComponente from './components/PrimeiroComponente.vue'
import LifeCycle from './components/LifeCycle.vue'
import Pessoa from './components/Pessoa.vue'
import Header from './components/Header.vue'

export default {
  name: 'App',
  components: {
    PrimeiroComponente,
    LifeCycle,
    Pessoa,
    Header
  },
  data(){
    return {
      email: 'ayrton2@server.com'
    }
  }
}
</script>

<style>
body {
  background-color: black;
  color: white;
}
</style>