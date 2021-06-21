<template>
    <h2>Tipo de Cuenta: {{cuenta}}</h2>
    <h2>Saldo: ${{saldo}}</h2>
    <h2>Cuenta: {{ estado ? 'Activa' : 'Desactivada' }}</h2>
    <div v-for="(servicio, index) in servicios" :key="index">
        {{index + 1}}.-{{ servicio }}
    </div><br>

    <AccionSaldo 
        texto="Aumentar saldo"
        @accion="aumentar"
    />
    <AccionSaldo 
        texto="Disminuir saldo"
        @accion="disminuir"
        :disabled="desactivar"
        
    />

</template>

<script>
import AccionSaldo from './AccionSaldo.vue'

export default {
    components: {
        AccionSaldo
    },
    data() {
        return {
            saldo: 1000,
            cuenta: 'Visa',
            estado: true,
            servicios: ['Giro', 'Abono', 'Transferencia'],
            desactivar: false

        }
    },
    methods: {
        aumentar(){
            this.saldo = this.saldo + 100
            this.desactivar = false
        },
        disminuir(){
            if(this.saldo === 0){
                alert('saldo agotado')
                this.desactivar = true
            } else {
                this.saldo = this.saldo - 100
            }
            
        }
    }
}
</script>

<style>

</style>