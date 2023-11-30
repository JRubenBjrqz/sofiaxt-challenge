<script setup>
import Book from "../Course/Book.vue";
import Dropdown from "../Course/Dropdown.vue";
import FAB from "../Course/FAB.vue";
</script>

<template>
    <Dropdown dropdownText="Los más populares" class="ps-5 pt-4 slider-background"/>
    <div id="carousel-popular" class="carousel carousel-dark slide slider-background" data-bs-ride="false">
        <div class="carousel-inner">
            <div class="carousel-item active">
                <div class="container-fluid">
                    <div class="row py-3">
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                :bookNumber="1"
                                bookHeader="1°"
                                bookCover="https://humanidades.com/wp-content/uploads/2017/07/geografia-1-e1571191548230.jpg"
                                bookTitle="Geografía Secundaria"
                                bookDescription="Irma Mendoza"
                                bookThemes="20 temas"
                                :isBookmarkActive="true"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book
                                :bookNumber="2" 
                                bookHeader="2°"
                                bookCover="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSHM5MlPugZuoToTM-uuBmDgqvlnuAnG3ijSA&usqp=CAU"
                                bookTitle="Historia Universal"
                                bookDescription="Eduardo Mexía"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book
                                :bookNumber="3" 
                                bookHeader="3°"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Diana Padilla"
                                bookThemes="20 temas"
                                :isBookmarkActive="true"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                :bookNumber="1"
                                bookHeader="+1"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Hector Castro"
                                bookThemes="20 temas"
                                :isDownloadActive="true"
                                :isBookmarkActive="true"
                            />
                        </div>     
                    </div>
                </div>
            </div>
        </div>
        <div>
            <a class="carousel-control-next" href="#carousel-popular" role="button" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Next</span>
            </a>
        </div>
    </div>
    <FAB class="position-absolute end-0 z-3"/>
    <h5 class="ps-5 pt-4 pb-0 m-0">Secundaria</h5>
    <div id="carousel-high-school" class="carousel carousel-dark slide" data-bs-ride="false">
        <div class="carousel-inner">
            <div class="carousel-item active">
                <div class="container-fluid">
                    <div class="row py-3">
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book
                                :bookNumber="1" 
                                bookHeader="1°"
                                bookCover="https://humanidades.com/wp-content/uploads/2017/07/geografia-1-e1571191548230.jpg"
                                bookTitle="Geografía Secundaria"
                                bookDescription="Irma Mendoza"
                                bookThemes="20 temas"
                                :isBookmarkActive="true"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book
                                :bookNumber="2" 
                                bookHeader="2°"
                                bookCover="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSHM5MlPugZuoToTM-uuBmDgqvlnuAnG3ijSA&usqp=CAU"
                                bookTitle="Historia Universal"
                                bookDescription="Eduardo Mexía"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book
                                :bookNumber="3" 
                                bookHeader="3°"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Diana Padilla"
                                bookThemes="20 temas"
                                :isBookmarkActive="true"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                :bookNumber="1"
                                bookHeader="+1"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Hector Castro"
                                bookThemes="20 temas"
                                :isDownloadActive="true"
                                :isBookmarkActive="true"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div>
            <a class="carousel-control-next" href="#carousel-high-school" role="button" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Next</span>
            </a>
        </div>
    </div>
</template>

<style scoped>
.slider-background {
    background-color: var(--gray-color);
}
</style>
