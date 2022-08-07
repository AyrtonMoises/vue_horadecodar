<template>
    <h1>Nome e: {{ nome }}</h1>
</template>

<script>
export default {
    name: 'LifeCycle',
    data() {
        return {
            nome: 'Ainda n sei'
        }
    },
    created(){
        this.nome = "Ayrton"
        this.lifeCycle()

    },
    mounted(){
        setTimeout(() => {
            this.nome = 'Tinho'
        }, 3000)
    },
    methods: {
        lifeCycle(){
            console.log('funciono aqui tbm')
        }
    }
}
</script>