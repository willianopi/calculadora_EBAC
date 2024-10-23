<template>
    <div class="mb-3">
        <label class="form-label">{{ label }}</label>
        <input type="number" class="form-control" v-model="valor" @input="atualizarValor" />
    </div>
</template>

<script>
export default {
    name: 'CampoNumerico',
    props: {
        modelValue: {
            type: Number,
            required: true
        },
        label: {
            type: String,
            required: true
        }
    },
    data() {
        return {
            valor: this.modelValue
        }
    },
    methods: {
        atualizarValor() {
            this.$emit('update:modelValue', this.valor);
        }
    },
    watch: {
        modelValue(newValue) {
            this.valor = newValue;
        }
    }
}
</script>

<style scoped>
</style>