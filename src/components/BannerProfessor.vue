<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  professorCover: String,
  professorPicture: String,
  professorFullName: String,
  proffesorFirstAchievement: String,
  proffesorSecondAchievement: String,
});
</script>

<template>
    <img :src="professorCover" class="professor-cover"/>
    <div class="professor-headline">
        <img :src="professorPicture"/> 
        <h2>{{ professorFullName }}</h2>
        <div class="d-flex">
            <div class="me-2">
                <i class="bi bi-star-fill text-warning me-1"></i>
                <span>{{ proffesorFirstAchievement }}</span>
            </div>
            <div>
                <i class="bi bi-star-fill text-warning me-1"></i>
                <span>{{ proffesorSecondAchievement }}</span>
            </div>
        </div>
    </div>
</template>

<style scoped>
.professor-cover {
    width: 100%;
    height: 104px;
}
.professor-headline {
  padding: 16px 8px 32px 16px;
  background-color: var(--gray-color);
}
.professor-headline img{
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
.professor-headline h2 {
    margin: 0;
    padding: 0;
    font-size: 16px;
    color: var(--primary-color);
    font-weight: bold;   
}
.professor-headline span {
    font-size: 12px;
    color:#707070;
}

.user-profile-headline i {
  font-size: 10px;
}

</style>