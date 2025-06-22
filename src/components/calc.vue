<script setup>

import { reactive } from 'vue'

const estado = reactive({
    operacao: '+',
    val1: 0,
    val2: 0,
    resultado: 0
    
})

const CalcularResultado = ()=>{
    switch (estado.operacao){
        case "*":
            estado.resultado = estado.val1 * estado.val2
            break
        case "-":
            estado.resultado = estado.val1 - estado.val2
            break
        case "/":
            estado.resultado = estado.val1 / estado.val2
            break
        case "+":
            estado.resultado = estado.val1 + estado.val2
            break
    }
    console.log(estado.resultado)
}

</script>

<template>
    <div class="calc">
        <input @input="evento =>{estado.val1 = parseFloat(evento.target.value)
            CalcularResultado()
        }"  type="number" value="0" class="form-control ajust-form col-sm-2">
        <select @change="evento =>{
            estado.operacao = evento.target.value;
            CalcularResultado()
        }" class="form-control col-sm-2">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="*">*</option>
            <option value="/">/</option>
        </select>
        <input @input="evento =>{estado.val2 = parseFloat(evento.target.value)
            CalcularResultado()}"  type="number" value="0" class="form-control ajust-form col-sm-2">
    </div>
    <h1 :class="estado.resultado >= 0 ? 'positivo' : 'negativo'" class="mt-3">Resultado é {{ estado.resultado }}</h1>
</template>

<style scoped>
.ajust-form{
    max-width: 20vw;
    text-align: center;
    font-size: 18pt;
}
.positivo{
    color: green;
}

.negativo{
    color: red;
}

.calc{
    display: flex;
    justify-content: center;
}

select{
    margin: 0 2vw;
    font-size: 18pt;
    text-align: center;
    max-width: 5vw;
    font-weight: bold;
}
</style>