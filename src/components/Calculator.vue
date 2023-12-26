<template>
    <div>
        <h1>Calculator</h1>
        <div class="calculator">
            <div class="display">{{ result }}</div>
            <div class="buttons">
                <button @click="appendToInput('1')">1</button>
                <button @click="appendToInput('2')">2</button>
                <button @click="appendToInput('3')">3</button>
                <button @click="setOperator('+')">+</button>
                <button @click="appendToInput('4')">4</button>
                <button @click="appendToInput('5')">5</button>
                <button @click="appendToInput('6')">6</button>
                <button @click="setOperator('-')">-</button>
                <button @click="appendToInput('7')">7</button>
                <button @click="appendToInput('8')">8</button>
                <button @click="appendToInput('9')">9</button>
                <button @click="setOperator('*')">*</button>
                <button @click="appendToInput('0')">0</button>
                <button @click="clearInput">C</button>
                <button @click="calculateResult">=</button>
                <button @click="setOperator('/')">/</button>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

// State
const input = ref('');
const result = ref('');

// Methods
const appendToInput = (value) => {
    input.value += value;
};

const setOperator = (operator) => {
    if (input.value !== '') {
        input.value += ` ${operator} `;
    }
};

const clearInput = () => {
    input.value = '';
    result.value = '';
};

const calculateResult = () => {
    try {
        result.value = eval(input.value).toString();
    } catch (error) {
        result.value = 'Error';
    }
};
</script>

<style scoped>
.calculator {
    max-width: 300px;
    margin: 0 auto;
    text-align: center;
    background-color: aqua;
}

.display {
    font-size: 2em;
    margin-bottom: 10px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    padding: 10px;
    font-size: 1.2em;
    cursor: pointer;
}
</style>
