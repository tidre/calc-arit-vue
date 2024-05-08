<script setup>
    const props = defineProps(['realizaOperacao', 'setValor1', 'setValor2', 'valor1Temp', 'valor2Temp', 'trocarOperacao'])
</script>

<template>
    <form>
        <div class="row">
            <div class="col">
                <input @keyup="props.setValor1" @change="props.realizaOperacao" required type="text" placeholder="Valor 1" class="form-control">
                <input @keyup="props.setValor2" @change="props.realizaOperacao" required type="text" placeholder="Valor 2" class="form-control">
            </div>
            <div class="col-md-2">
                <select @change="props.trocarOperacao" class="form-control">
                    <option value="soma">Soma</option>
                    <option value="subtracao">Subtracao</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>