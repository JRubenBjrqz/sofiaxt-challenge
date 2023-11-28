<template>
    <div>
      <header class="header" :class="{ 'body-pd': isHeaderPd }" id="header">
        <div class="header_toggle">
          <i class="bi bi-list" @click="toggleNavbar" id="header-toggle"></i>
        </div>
        <!-- <div class="header_img">
          <img src="https://i.imgur.com/hczKIze.jpg" alt="" />
        </div> -->
      </header>
      <div class="sidenavbar" :class="{ 'show': isNavbarVisible }" id="nav-bar">
        <nav class="nav">
          <div>
            <a href="#" class="nav_logo">
              <img src="https://www.sofiaxt.com/favicon-16x16.png" alt="" class="nav_logo-icon">
              <span class="nav_logo-name">SofíaXT</span>
            </a>
            <a href="#" class="nav_link" @click="preventDefault">
                <i class="bi bi-house nav_icon"></i>
                <span>Inicio</span>
            </a>
            <div class="nav_list">
              <a href="#" class="nav_link active" @click="setActiveLink(1)">
                <i class="bi bi-people nav_icon"></i>
                <span>Grupos</span>
              </a>
              <!-- Resto de enlaces aquí -->
              <a href="#" class="nav_link" @click="setActiveLink(2)">
                <i class="bi bi-journal nav_icon"></i>
                <span>Smartbooks</span>
              </a>
              <a href="#" class="nav_link" @click="setActiveLink(3)">
                <i class="bi bi-gear nav_icon"></i>
                <span>Utilidades</span>
              </a>
              <a href="#" class="nav_link" @click="setActiveLink(4)">
                <i class="bi bi-magic nav_icon"></i>
                <span>Tour Virtual</span>
              </a>
              <a href="#" class="nav_link" @click="setActiveLink(5)">
                <i class="bi bi-info-circle nav_icon"></i>
                <span>Soporte</span>
              </a>
            </div>
          </div>
        </nav>
      </div>
      <!-- Resto del contenido HTML -->
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isNavbarVisible: false,
        isHeaderPd: false,
        activeLink: null
      };
    },
    methods: {
      toggleNavbar() {
        this.isNavbarVisible = !this.isNavbarVisible;
        this.isHeaderPd = !this.isHeaderPd;
      },
      setActiveLink(linkNumber) {
        this.activeLink = linkNumber;
        // Aquí puedes realizar otras acciones si es necesario al establecer el enlace activo
      },
      preventDefault(event) {
        event.preventDefault();
      }
    },
    mounted() {
      const linkColor = document.querySelectorAll(".nav_link");
      linkColor.forEach((l) => l.addEventListener("click", this.colorLink));
    },
    beforeUnmount() {
      const linkColor = document.querySelectorAll(".nav_link");
      linkColor.forEach((l) => l.removeEventListener("click", this.colorLink));
    },
    created() {
      document.addEventListener("DOMContentLoaded", () => {
        const showNavbar = (toggleId, navId, bodyId, headerId) => {
          const toggle = document.getElementById(toggleId),
            nav = document.getElementById(navId),
            bodypd = document.getElementById(bodyId),
            headerpd = document.getElementById(headerId);
  
          if (toggle && nav && bodypd && headerpd) {
            toggle.addEventListener("click", () => {
              nav.classList.toggle("show");
              toggle.classList.toggle("bi-x");
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
    a {
      text-decoration: none;
    }

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

    .header_toggle {
      color: var(--white-color);
      font-size: 1.5rem;
      cursor: pointer;
    }

    .header_img {
      width: 35px;
      height: 35px;
      display: flex;
      justify-content: center;
      border-radius: 50%;
      overflow: hidden;
    }

    .header_img img {
      width: 40px;
    }

    .sidenavbar {
      position: fixed;
      top: 0;
      left: -30%;
      width: var(--sidenav-width);
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

    .nav_logo,
    .nav_link {
      display: grid;
      grid-template-columns: max-content max-content;
      align-items: center;
      column-gap: 1rem;
      padding: .5rem 0 .5rem 1.5rem;
    }

    .nav_logo {
      margin-bottom: 2rem;
    }

    .nav_logo-icon {
      font-size: 1.25rem;
      padding-right: 1rem;
      color: var(--white-color);
    }

    .nav_logo-name {
      color: var(--font-color);
      font-weight: 600;
    }

    .nav_link {
      position: relative;
      color: var(--font-color);
      margin-bottom: 0.125rem;
      transition: .3s;
    }

    .nav_link:hover {
      color: var(--primary-color);
    }

    .nav_icon {
      font-size: 1.25rem;
      padding-right: 1rem;
    }

    .show {
      left: 0;
    }

    .body-pd {
      padding-left: calc(var(--sidenav-width) + 1rem);
    }

    .active {
      color: var(--primary-color);
      background-color: var(--gray-color);
    }

    .height-100 {
      height: 100vh;
    }

    @media screen and (min-width: 768px) {
      body {
        margin: calc(var(--header-height) + 1rem) 0 0 0;
        padding-left: calc(var(--sidenav-width) + 2rem);
      }

      .header {
        height: calc(var(--header-height) + 1rem);
        padding: 0 2rem 0 calc(var(--sidenav-width) + 2rem);
      }

      .header_img {
        width: 40px;
        height: 40px;
      }

      .header_img img {
        width: 45px;
      }

      .sidenavbar {
        left: 0;
        padding: 1rem 0 0 0;
      }

      .show {
        width: calc(var(--sidenav-width) + 132px);
      }

      .body-pd {
        padding-left: calc(var(--sidenav-width) + 188px);
      }
    }
</style>