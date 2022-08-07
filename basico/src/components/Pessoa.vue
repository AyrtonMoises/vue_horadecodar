<template>
    <div>
        <form @submit="enviarFormulario($event)">
            <input type="text" placeholder="nome" v-model="nome">
            <input type="text" placeholder="email" v-model="email">
            <input type="submit">
        </form>
        <div class="paragrafo-pai">
        <ul>
            <li v-for="(tech, index) in backend_techs" v-bind:key="index">
                {{ tech }}
            </li>
        </ul>
        <ul>
            <li v-for="tech in frontend_techs" :key="tech.id">
                {{ tech.desc }}
            </li>
        </ul>
        <p v-if="esta_trabalhando">Estou trabalhando</p>
        <p v-else>Nao estou trabalhando</p>
        <p v-if="4 > 2">OK</p>
        </div>
        <div>
            <button @click="showEmail">{{ textoBotao }}</button>
        </div>
        <p v-show="mostrar_email">Manda email para {{ email }}</p>
        <p>Para acessar meu portfólio <a v-bind:href="meu_link">Clique aqui</a></p>
        <Picture />

    </div>
</template>

<script>
import Picture from './Picture.vue'

export default {

    name: 'Pessoa',
    data() {
        return {
            nome: "",
            esta_trabalhando: false,
            mostrar_email: false,
            meu_link: 'https://google.com',
            textoBotao: 'Mostrar email',
            backend_techs: ['Python', 'JS', 'PHP'],
            frontend_techs: [
                {id: 1, desc: 'Vue'},
                {id: 2, desc: 'React'},
                {id: 3, desc: 'Angular'},
            ]
        }
    },
    components: {
        Picture
    },
    methods: {
        showEmail(){
            this.mostrar_email = !this.mostrar_email
            if(!this.mostrar_email){
                this.textoBotao = 'Mostrar email'
            }else{
                this.textoBotao = 'Ocultar email'
            }
        },
        enviarFormulario(e){
            e.preventDefault();

            const nome = this.nome;
            const email = this.email;

            console.log(`meu nome:${nome} email:${email}`);
        }
    },
    props: {
        email: String
    }
    // props: ["email"] e possivel usar array mas sem typar
}
</script>

<style scoped>
.paragrafo-pai {
    color: red
}
</style>