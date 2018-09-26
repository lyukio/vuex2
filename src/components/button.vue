<script>
import { mapActions } from 'vuex';
export default {
    methods: {
        mudarDados() {
            const payload = {
                name: 'Outro nome',
                email: 'email@email.com',
                level: 'usuario-raso',
                city: 'Santo André',
                state: 'SP',
            }
            this.changeUser(payload)
        },
        ...mapActions(['changeUser'])
    },
    computed: {
        hasUser() {
            return this.$store.state.user.name !== ''
        }
    }
}
</script>


<template>
    <div>
        <button :disabled="!hasUser" @click="mudarDados">Mudar dados do usuário</button>
    </div>
</template>
