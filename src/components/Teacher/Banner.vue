<script setup>
import { defineProps } from "vue";
import Achievement from "../Teacher/Achievement.vue"

const props = defineProps({
  teacherCover: String,
  teacherPicture: String,
  teacherFullName: String,
});
</script>

<template>
    <div>
        <img :src="teacherCover" class="teacher-cover"/>
        <div class="teacher-headline">
            <img :src="teacherPicture"/> 
            <h2>{{ teacherFullName }}</h2>
            <div class="d-flex">
                <Achievement 
                    teacherAchievement="3.3M"
                />
                <Achievement 
                    teacherAchievement="Top 5 creadores de ejercicios"
                />
            </div>
        </div>
    </div>
</template>

<style scoped>
.teacher-cover {
    width: 100%;
    height: 104px;
}
.teacher-headline {
  padding: 16px 8px 32px 16px;
  background-color: var(--gray-color);
}
.teacher-headline img{
    position: relative;
    float: left;
    margin: -60px 20px 0  0;
    width: 96px;
    height: 96px;
    border: 3px solid #EBEFFF;
    border-radius: 8px;
    z-index: 90;
    object-fit: cover;
    object-position: 50% 50%;

}
.teacher-headline h2 {
    margin: 0;
    padding: 0;
    font-size: 16px;
    color: var(--primary-color);
    font-weight: bold;   
}
</style>