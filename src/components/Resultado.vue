<script setup>
defineProps(['resultado'])
</script>

<template>
    <div class="mt-3 text-center">

        <div class="win-result">
            <strong>Resultado:</strong> {{ resultado }}
        </div>

    </div>
</template>