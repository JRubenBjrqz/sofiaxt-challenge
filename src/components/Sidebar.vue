<template>
    <div id="body-pd">
      <header class="header" :class="{ 'body-pd': isHeaderPd }" id="header">
        <div class="header_toggle">
          <i class="bi bi-list" @click="toggleNavbar" id="header-toggle"></i>
        </div>
        <div class="d-flex px-3 py-1 header-dropdown rounded-pill">
          <span class="header_font">Hi, Roshan</span>
          <div class="px-3">
            <i class="bi bi-clock header_icon"></i>
            <i class="bi bi-bell header_icon"></i>
          </div>
          <div class="header_img">
          <img src="https://i.imgur.com/hczKIze.jpg" alt="" />
        </div>
        </div>
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
      <div class="vh-100 bg-info">
        <div class="user_profile_cap">
          <div class="user_profile_cover">
            <img src="https://htmlcolorcodes.com/assets/images/colors/white-color-solid-background-1920x1080.png" alt="img"/>
          </div>
          <div class="user_profile_headline">
              <img src="https://pbs.twimg.com/profile_images/1313073227594424321/hjnEFEWd_400x400.jpg" alt="img"/> 
              <h2>Eduardo Mexia</h2>
              <div class="d-flex">
                <div class="me-2">
                  <i class="bi bi-star-fill text-warning"></i>
                  <span> 3.3M</span>
                </div>
                <div>
                  <i class="bi bi-star-fill text-warning"></i>
                  <span> Top 5: Mejores creadores de ejercicios</span>
                </div>
              </div>
          </div>
        </div>
        <div>
          <div class="container">
            <div class="row">
              <div class="column">
                <button class="btn btn-primary">
                General
              </button>
              <button class="btn btn-primary">
                Mis libros
              </button>
              <button class="btn btn-primary">
                Mis favoritos
              </button>
              <button class="btn btn-primary">
                Bibliotecas de sofia xt
              </button>
              </div>
            </div>
          </div>
        </div>
      </div>
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
      width: 24px;
      height: 24px;
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
      #body-pd {
        margin: calc(var(--header-height) + 1rem) 0 0 0;
        padding-left: calc(var(--sidenav-width) + 2rem);
      }

      .header {
        height: calc(var(--header-height) + 1rem);
        padding: 0 2rem 0 calc(var(--sidenav-width) + 2rem);
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

    .header_icon {
      font-size: 1rem;
      color: var(--white-color);
    }

    .header_font {
      font-size: 1rem;
      color: var(--white-color);
    }

    .header-dropdown {
      background-color: #5fa6d3;
    }

    .user_profile_cap {
      width: 970;
      height: auto 13;
    }

.user_profile_headline {
  padding: 20px;
  font-size: 16px;
  background-color: var(--gray-color);
}
.user_profile_headline img{
    border: 1px solid #EEEEEE;
    width: 96px;
    height: 96px;
    float: left;
    margin: -70px 10px 0  0;
    position: relative;
    z-index: 111;
}
.user_profile_headline h2 {
    margin: 0;
    padding: 0;
    font-size: 16px;
    color: var(--primary-color);
    font-weight: bold;
    display: block;   
}
.user_profile_headline span {
    font-size: 12px;
    color:gray;
}

.user-profile-headline i {
  font-size: 10px;
}

.user_profile_cover img {
    width: 100%;
    height: 160px;
    -webkit-border-top-left-radius: 5px;
    -webkit-border-top-right-radius: 5px;
    -moz-border-radius-topleft: 5px;
    -moz-border-radius-topright: 5px;
    border-top-left-radius: 5px;
    border-top-right-radius: 5px;
  }

</style>