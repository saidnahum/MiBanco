<template>
    <h1>{{texto}}</h1>
</template>

<script>
export default {
    name: 'Titulo',
    props: {
        texto: String
    }
}
</script>

<style scoped>
    h1 {
        color: peru;
    }
</style>

<!-- El scope sirve para utilizar solo los estilos en el componente actual y no en los demás -->