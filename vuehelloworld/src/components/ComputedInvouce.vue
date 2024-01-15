<template>
    <div>
        <label>Subtotal</label>
        <input type="number" v-model="subTotal"/>
        <h3>Total taxes payable: {{ totalVat}} ({{ vat }} %)</h3>
    </div>
</template>
<script lang="ts" setup>
import { ref, Ref, computed } from 'vue';
const subTotal:Ref<number> = ref(10);
const vat = 3; // VAT rate in percentages.
// Calculate the value of VAT on the subTotal amount.
const totalVat:Ref<string> = computed(() => `= ${parseFloat((subTotal.value * vat / 100).toFixed(2))}`);

</script>

<style scoped>
</style>