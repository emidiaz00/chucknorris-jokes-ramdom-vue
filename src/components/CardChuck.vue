<template>
    <div>
        <p>{{ value }}</p>
        <button @click="getRamdomQuoteChuck">Get quote</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            value: null
        }
    },
    methods: {
        async getRamdomQuoteChuck() {
            const { value } = await fetch("https://api.chucknorris.io/jokes/random").then(response => response.json())
            this.value = value;
        }
    },
}
</script>
<style>
body {
    background-image: url('../assets/chuck.jpg');
    background-size: cover; /* establece el tamaño de la imagen para cubrir todo el elemento */
    background-repeat: no-repeat; /* evita que la imagen se repita */
}
button {
    background-color: rgb(72, 172, 138);
    border: none;
    border-radius: 4px;
    padding: 10px;
    color: #fff;
    font-weight: bold;
    text-transform: uppercase;
    position: relative;
    margin-top: 50px;
}
button:hover {
    cursor: pointer;
    background-color: rgb(50, 117, 95);
}
p {
    font-weight: bold;
}


</style>