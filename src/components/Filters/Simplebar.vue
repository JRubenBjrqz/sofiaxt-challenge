<script setup>
import { defineProps } from "vue";
import Button from "../Filters/Button.vue";

const props = defineProps({
});
</script>

<template>
 <div>
    <div class="container-fluid">
        <div class="row">
            <div class="col-12 col-lg-7 d-flex justify-content-between align-items-center px-0 pt-4 pb-3">
                <Button buttonText="General" />
                <Button buttonText="Mis libros" />
                <Button buttonText="Mis favoritos" />
                <Button buttonText="Bibliotecas de sofiaxt" />
            </div>
            <div class="col-2 col-lg-1 d-flex justify-content-center align-items-center pt-4 pb-3">
                <i class="bi bi-funnel filter-icon"></i>
            </div>
            <div class="col-10 col-lg-4 d-flex justify-content-between align-items-center pt-4 pb-3">
                <div class="input-group">
                    <span class="input-group-text"><i class="bi bi-search search-icon"></i></span>
                    <input type="text" class="form-control form-control-sm" placeholder="Buscar tema, libro, nivel, autor">
                </div>
            </div>
        </div>
    </div>
</div>   
</template>

<style scoped>
    .filter-icon {
        font-size: 24px;
        color: gray;
    }

    .search-icon {
        color: var(--primary-color);
    }
</style>