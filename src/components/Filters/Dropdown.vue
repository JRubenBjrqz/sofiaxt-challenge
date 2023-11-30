<script setup>
import { defineProps } from "vue";

const props = defineProps({
  dropdownText: String,
});
</script>

<template>
    <div class="dropdown">
        <button class="btn button-slider" type="button" data-bs-toggle="dropdown" aria-expanded="false">
            {{ dropdownText }}
            <i class="bi bi-chevron-down dropdown-icon"></i>
        </button>
        <ul class="dropdown-menu">
            <li>
                <a class="dropdown-item" href="#">Biblioteca 1</a>
            </li>
            <li>
                <a class="dropdown-item" href="#">Biblioteca 2</a>
            </li>
        </ul>
    </div>
</template>

<style scoped>
.button-slider {
    font-size: 16px;
    color: var(--font-color);
    background-color: transparent;
    border: none;
}

.button-slider:hover {
    color: var(--primary-color);
    transition: 0.3s;
}

.dropdown-icon {
    color: var(--primary-color);
}

.dropdown-menu {
    border: none !important;
}
</style>