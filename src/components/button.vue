<script>
export default {
    methods: {
        mudarDados() {
            const payload = {
                name: 'Outro nome',
                email: 'email@email.com',
                level: 'usuario-raso'
            }
            this.$store.commit('CHANGE_USER', payload)
        }
    }
}
</script>


<template>
    <div>
        <button @click="mudarDados">Mudar dados do usuário</button>
    </div>
</template>
