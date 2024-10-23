<template>
    <div class="container d-flex justify-content-center align-items-center" style="height: 100vh;">
        <div class="card shadow p-4" style="width: 350px;">
            <h2 class="text-center">Calculadora Aritmética</h2>
            <CampoNumerico v-model="numero1" label="Número 1" />
            <CampoNumerico v-model="numero2" label="Número 2" />

            <div class="mb-3">
                <label class="form-label">Operação</label>
                <select v-model="operacao" class="form-select">
                    <option value="+">+</option>
                    <option value="-">-</option>
                    <option value="*">*</option>
                    <option value="/">/</option>
                </select>
            </div>

            <h4 class="text-center">Resultado: {{ resultado }}</h4>
        </div>
    </div>
</template>

<script>
import CampoNumerico from './CampoNumerico.vue';

export default {
    name: 'CalculadoraAritmetica',
    components: {
        CampoNumerico
    },
    data() {
        return {
            numero1: 0,
            numero2: 0,
            operacao: '+'
        }
    },
    computed: {
        resultado() {
            switch (this.operacao) {
                case '+':
                    return this.numero1 + this.numero2;
                case '-':
                    return this.numero1 - this.numero2;
                case '*':
                    return this.numero1 * this.numero2;
                case '/':
                    return this.numero2 !== 0 ? this.numero1 / this.numero2 : 'Erro: Divisão por zero';
                default:
                    return 0;
            }
        }
    }
}
</script>

<style scoped>
.card {
    background-color: #fae4d3;
}
</style>