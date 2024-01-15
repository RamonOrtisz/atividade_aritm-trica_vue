<template>
    <div class="container p-5 text-center">
        <h1>Calculadora Aritmética</h1>
        <div class="mt-5">
            <label class="d-block" for="numero1">Número 1:</label>
            <input class="borda text-center" type="number" v-model="numero1" @input="calcularResultado" />
        </div>

        <div class="mt-3">
            <label class="d-block" for="numero2">Número 2:</label>
            <input class="borda text-center" type="number" v-model="numero2" @input="calcularResultado" />
        </div>

        <div class="p-5">
            <label for="operacao" class="p-2">Operação:</label>
            <select class="bordaQuadrada" v-model="operacao" @change="calcularResultado">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
        </div>

        <div>
            <label class="d-block p-3" for="resultado">Resultado:</label>
            <input class="borda text-center" type="text" v-model="resultado" readonly />
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            numero1: 0,
            numero2: 0,
            operacao: '+',
            resultado: 0,
        };
    },
    methods: {
        calcularResultado() {
            switch (this.operacao) {
                case '+':
                    this.resultado = this.numero1 + this.numero2;
                    break;
                case '-':
                    this.resultado = this.numero1 - this.numero2;
                    break;
                case '*':
                    this.resultado = this.numero1 * this.numero2;
                    break;
                case '/':
                    this.resultado = this.numero1 / this.numero2;
                    break;
            }
        },
    },
};
</script>

<style>
.container {
    margin-top: 200px;
    border-radius: 20px ;
    background-color: #ccc;
}
.bordaQuadrada{
    padding: 5px;
    border-radius: 10px ;
}
.borda {
    padding: 10px;
    border-radius: 20px;
}

@media (max-width: 676px) {
    .container {
        max-width: 78%;
    }
}

</style>