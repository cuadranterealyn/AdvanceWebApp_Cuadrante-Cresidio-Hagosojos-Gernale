<script setup>
import { ref } from 'vue'

const input = ref('')
</script>
<template>
    <!-- reactivity -->
    <!-- two-way binding -->
    <!-- directives (v-model) -->
    <select v-model="input">
        <option value="web">web</option>
        <option value="net">net</option>
        <option value="others">others</option>
    </select>
    <p>p: {{ input }}</p>
    <!-- conditional -->
    <p v-if="input == 'web'">
    <p>Web Development</p>
    </p>
    <p v-else-if="input == 'net'">Networking</p>
    <p v-else>Others</p>

    <p v-if="input == 'web'">
    <p>Web Development 2.0</p>
    </p>
    <!-- commit and push -->
</template>