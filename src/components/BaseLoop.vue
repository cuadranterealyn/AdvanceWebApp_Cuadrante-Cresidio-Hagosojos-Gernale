<script setup>
import { ref } from 'vue';

// Data property
const strings = ref(['Cuadrante', 'Cresidio', 'Gernale', 'Hagosojos']);
let loopIndex = ref(0);
const showBSITText = ref(false);

// Method to continue the loop
const continueLoop = () => {
    strings.value.push("BSIT Block-4 Students");
};
</script>

<template>
    <div>
        <ul>
            <!-- Example: Using v-for to loop through name -->
            <li v-for="name in strings " :key=" name" style="font-style: italic;">{{ name  }}</li>
        </ul>
        <button @click="continueLoop">Continue Loop</button>
       
    </div>

</template>
