<template>
  <div id="body-pd">
    <header class="header" :class="{ 'body-pd': isHeaderPadding }" id="header">
      <div class="header-toggle">
        <i class="bi bi-list" @click="toggleNavbar" id="header-toggle"></i>
      </div>
      <HeaderProfile 
        userFirstName="Roshan" 
        userPicture="https://media.istockphoto.com/id/1391298352/photo/attractive-caucasian-smiling-handsome-man-in-blue-t-shirt-looking-right.webp?b=1&s=170667a&w=0&k=20&c=U8Dzr0a7lNHzdAhZpIXIglvPMADeMiU49cAdegCoO-4="
      />
    </header>
    <div class="sidebar" :class="{ 'show': isNavbarVisible }" id="nav-bar">
      <nav class="nav">
        <div>
          <a href="#" class="nav-logo">
            <img src="https://www.sofiaxt.com/favicon-16x16.png" class="nav-logo-icon">
            <span class="nav-logo-name">SofíaXT</span>
          </a>
          <a href="#" class="nav-link active">
              <i class="bi bi-house nav_icon"></i>
              <span>Inicio</span>
          </a>
          <div class="nav_list">
            <a href="#" class="nav-link">
              <i class="bi bi-people nav_icon"></i>
              <span>Grupos</span>
            </a>
            <a href="#" class="nav-link">
              <i class="bi bi-journal nav_icon"></i>
              <span>Smartbooks</span>
            </a>
            <a href="#" class="nav-link">
              <i class="bi bi-gear nav_icon"></i>
              <span>Utilidades</span>
            </a>
            <a href="#" class="nav-link">
              <i class="bi bi-magic nav_icon"></i>
              <span>Tour Virtual</span>
            </a>
            <a href="#" class="nav-link">
              <i class="bi bi-info-circle nav_icon"></i>
              <span>Soporte</span>
            </a>
          </div>
        </div>
      </nav>
    </div>
    <!-- Resto del contenido HTML -->
    <div class="vh-100">
      <TeacherBanner
        teacherCover="https://htmlcolorcodes.com/assets/images/colors/white-color-solid-background-1920x1080.png" 
        teacherPicture="https://images.pexels.com/photos/7092613/pexels-photo-7092613.jpeg?cs=srgb&dl=pexels-rdne-stock-project-7092613.jpg&fm=jpg"
        teacherFullName="Eduardo Mexía"
      />
      <Simplebar/>
      <Slider/>
      <Slider/>
    </div>
  </div>
</template>
  
<script>
import HeaderProfile from '../components/Header/Profile.vue';
import TeacherBanner from '../components/Teacher/Banner.vue';
import Simplebar from '../components/Filters/Simplebar.vue';
import Slider from '../components/Course/Slider.vue';

export default {
  components: { 
    HeaderProfile,
    TeacherBanner,
    Simplebar,
    Slider
  },
  data() {
    return {
      isNavbarVisible: false,
      isHeaderPadding: false,
    };
  },
  methods: {
    toggleNavbar() {
      this.isNavbarVisible = !this.isNavbarVisible;
      this.isHeaderPadding = !this.isHeaderPadding;
    },
  },
  created() {
    document.addEventListener("DOMContentLoaded", () => {
      const showNavbar = (toggleId, navId, bodyId, headerId) => {
          toggle = document.getElementById(header-toggle),
          nav = document.getElementById(nav-bar),
          bodypd = document.getElementById(body-pd),
          headerpd = document.getElementById(header);

        if (toggle && nav && bodypd && headerpd) {
          toggle.addEventListener("click", () => {
            nav.classList.toggle("show");
            bodypd.classList.toggle("body-pd");
            headerpd.classList.toggle("body-pd");
          });
        }
      };

      showNavbar("header-toggle", "nav-bar", "body-pd", "header");
    });
  }
};
</script>

<style scoped>
.header {
  width: 100%;
  height: var(--header-height);
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 1rem;
  background-color: var(--primary-color);
  z-index: var(--z-fixed);
  transition: .5s;
}

.header-toggle {
  font-size: 1.5rem;
  color: var(--white-color);
  cursor: pointer;
}

.sidebar {
  position: fixed;
  top: 0;
  left: -30%;
  width: var(--sidebar-width);
  height: 100vh;
  background-color: var(--white-color);
  padding: .5rem 0 0 0;
  transition: .5s;
  z-index: var(--z-fixed);
}

.nav {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;
}

.nav-logo,
.nav-link {
  display: grid;
  grid-template-columns: max-content max-content;
  align-items: center;
  column-gap: 1rem;
  padding: .5rem 0 .5rem 1.5rem;
}

.nav-logo {
  margin-bottom: 2rem;
}

.nav-logo-icon {
  font-size: 1.25rem;
  padding-right: 1rem;
  color: var(--white-color);
}

.nav-logo-name {
  color: var(--font-color);
  font-weight: 600;
}

.nav-link {
  position: relative;
  color: var(--font-color);
  margin-bottom: 0.125rem;
  transition: .3s;
}

.nav-link:hover {
  color: var(--primary-color);
}

.nav_icon {
  font-size: 1.25rem;
  padding-right: 1rem;
}

.active {
  color: var(--primary-color);
  background-color: var(--gray-color);
}

.show {
  left: 0;
}

.body-pd {
  padding-left: calc(var(--sidebar-width) + 1rem);
}

.height-100 {
  height: 100vh;
}

@media screen and (min-width: 768px) {
  #body-pd {
    margin: calc(var(--header-height) + 1rem) 0 0 0;
    padding-left: calc(var(--sidebar-width) + 0.2rem);
  }

  .header {
    height: calc(var(--header-height) + 1rem);
    padding: 0 2rem 0 calc(var(--sidebar-width) + 2rem);
  }

  .sidebar {
    left: 0;
    padding: 1rem 0 0 0;
  }

  .show {
    width: calc(var(--sidebar-width) + 132px);
  }

  .body-pd {
    padding-left: calc(var(--sidebar-width) + 188px);
  }
}

</style>