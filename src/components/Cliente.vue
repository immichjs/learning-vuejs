<template>
    <div :class="{'cliente': !isPremium, 'cliente-premium': isPremium}">
        <h4>Nome: {{ cliente.nome }}</h4>
        <p>Email: {{ cliente.email }}</p>
        <p v-if="showIdade">Idade: {{ cliente.idade }}</p>
        <p v-else>O usuário escondeu a idade</p>
        <!-- <p v-show="showIdade">Idade: {{ cliente.idade }}</p>  -->
        <button @click="changeColor($event)">Mudar cor</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            isPremium: false
        }
    },
    props: {
        cliente: Object,
        showIdade: Boolean
    },
    methods: {
        changeColor($event) {
            console.log($event)
            this.isPremium = !this.isPremium
        }
    }
}
</script>

<style scoped>
    .cliente {
        background: #ECE5E3;
        max-width: 600px;
        padding: 2rem;
        margin-top: 1.5rem;
    }

    .cliente-premium {
        background: #2c2c2c;
        color: #fff;
        max-width: 600px;
        padding: 2rem;
        margin-top: 1.5rem;
    }
</style>