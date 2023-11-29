<script setup>
import Book from "../Course/Book.vue";
</script>

<template>
    <div id="carousel-popular" class="carousel slide" data-bs-ride="false">
        <div class="carousel-inner">
            <div class="carousel-item active">
                <div class="container-fluid slider-background">
                    <div class="row py-3">
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="1°"
                                bookCover="https://humanidades.com/wp-content/uploads/2017/07/geografia-1-e1571191548230.jpg"
                                bookTitle="Geografía Secundaria"
                                bookDescription="Irma Mendoza"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="2°"
                                bookCover="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSHM5MlPugZuoToTM-uuBmDgqvlnuAnG3ijSA&usqp=CAU"
                                bookTitle="Historia Universal"
                                bookDescription="Eduardo Mexía"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="3°"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Diana Padilla"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="+1"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Hector Castro"
                                bookThemes="20 temas"
                            />
                        </div>     
                    </div>
                </div>
            </div>
        </div>
        <div>
            <a class="carousel-control-prev" href="#carousel-popular" role="button" data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Previous</span>
            </a>
            <a class="carousel-control-next" href="#carousel-popular" role="button" data-bs-slide="next">
                <span class="carousel-control-next-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Next</span>
            </a>
        </div>
    </div>
    <div id="carousel-high-school" class="carousel slide" data-bs-ride="false">
        <div class="carousel-inner">
            <div class="carousel-item active">
                <div class="container-fluid">
                    <div class="row py-3">
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="1°"
                                bookCover="https://humanidades.com/wp-content/uploads/2017/07/geografia-1-e1571191548230.jpg"
                                bookTitle="Geografía Secundaria"
                                bookDescription="Irma Mendoza"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="2°"
                                bookCover="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSHM5MlPugZuoToTM-uuBmDgqvlnuAnG3ijSA&usqp=CAU"
                                bookTitle="Historia Universal"
                                bookDescription="Eduardo Mexía"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="3°"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Diana Padilla"
                                bookThemes="20 temas"
                            />
                        </div>
                        <div class="col-12 col-md-6 col-lg-3 p-3">
                            <Book 
                                bookNumber="+1"
                                bookCover="https://med.stanford.edu/news/all-news/2023/05/synthetic-biology-symposium/_jcr_content/main/image.img.620.high.jpg/synthbio.jpg"
                                bookTitle="Biología Secundaria"
                                bookDescription="Hector Castro"
                                bookThemes="20 temas"
                            />
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div>
            <a class="carousel-control-prev" href="#carousel-high-school" role="button" data-bs-slide="prev">
                <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                <span class="visually-hidden">Previous</span>
            </a>
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
