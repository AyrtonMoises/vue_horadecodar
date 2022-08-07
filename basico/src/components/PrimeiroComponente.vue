<template>
<div>
 <h1> Oi mundo</h1>
 <p> Nome {{ nome }}</p>
 <MultiplosEventos />
 <Reutilizacao />
 <Reutilizacao />
 <Reutilizacao />
</div>
</template>

<script>
import MultiplosEventos from './MultiplosEventos.vue';
import Reutilizacao from './Reutilizacao.vue';
 

export default {
  name: 'PrimeiroComponente',
  components: {
    MultiplosEventos,
    Reutilizacao
  },
  data(){
    return {
      nome: "Ayrton"
    }
  }
}
</script>
