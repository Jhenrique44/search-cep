<template>
  <nav class="nav-menu">
    <i class="fas fa-bars" @click="showMenu()"></i>

    <div class="nav-content" :class="this.showMobile ? 'open-menu' : 'closed-menu'">
      <div class="logo">Jhenrique44</div>
      <ul class="nav-items">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">About</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#contact">Contact</a></li>
        <li>
          <a href="https://github.com/Jhenrique44" target="_blank"><img src="../assets/GitHub.png" alt="Github" /></a>
        </li>
        <li>
          <a href="https://www.linkedin.com/in/joaohenriquefq/" target="_blank"><img src="../assets/linkedin-112.svg"
              alt="Linkedin" /></a>
        </li>
      </ul>
    </div>
  </nav>
</template>
<script>
export default {
  name: "Navbar",
  data() {
    return {
      showMobile: false,
    };
  },
  methods: {
    showMenu() {
      this.showMobile = !this.showMobile;
    },
  },
};
</script>
<style lang="scss" scoped>
.nav-menu {
  background-color: transparent;
}

.nav-content {
  display: flex;
  justify-content: space-between;
  padding: 30px;
  align-items: center;
}

.nav-items {
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;
  margin: 0;
  padding: 0;
  gap: 2rem;

  li {
    padding: 0 10px;

    a {
      text-decoration: none;
      color: #fff;
      font-size: 18px;
      font-weight: 500;

      img {
        height: 25px;
        width: 25px;
      }
    }
  }
}

i {
  display: none;
}

// Mobile version - hidden hamburger menu
@media screen and (max-width: 768px) {
  .nav-menu {
    padding-top: 10px;
    position: absolute;
    width: 100%;
  }

  .open-menu {
    opacity: 1;
    height: 150px;
  }

  .closed-menu {
    opacity: 0;
    height: 0;
    padding: 0;
  }

  .nav-content {
    flex-direction: column;
    z-index: 100;
    position: relative;
    transition: all 0.2s ease-out;
  }

  .nav-items {
    flex-direction: column;
  }

  i {
    display: block;
    text-align: right;
    padding: 0 10px 10px 0;
  }
}
</style>
