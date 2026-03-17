<script setup>
defineProps([
    'estado',
    'limparCalculadora'
])
</script>

<template>
    <div class="row g-2">

        <!-- Número 1 -->
        <div class="col">
            <input v-model.number="estado.numero1" type="number" class="form-control text-center" placeholder="1º número">
        </div>

        <!-- Operação -->
        <div class="col-md-3">
            <select v-model="estado.operacao" class="form-select text-center">
                <option value="+">+</option>
                <option value="-">-</option>
                <option value="*">*</option>
                <option value="/">/</option>
            </select>
        </div>

        <!-- Número 2 -->
        <div class="col">
            <input v-model.number="estado.numero2" type="number" class="form-control text-center" placeholder="2º número">
        </div>

        <!-- Botão -->
        <div class="col-12 mt-2">
            <button class="btn win-button w-100" @click="limparCalculadora">
                Limpar
            </button>
        </div>

    </div>
</template>