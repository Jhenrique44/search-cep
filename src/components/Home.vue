<template>
  <div class="container">
    <section id="Home" class="content-home">
      <div class="text-home">
        <h2>Hi, my name is</h2>
        <h1>João Henrique</h1>
        <h1 style="color: rgba(255, 255, 255, 0.75); font-size: 70px;">I am a Front-End Developer.</h1>
        <p style="margin-top: 2rem;">
          Currently a Front-End developer intern at Huawei, I'm also a student of Computer Engineering. I have been
          working
          with VueJs, utilizing HTML5 CSS3 and JavaScript to build <a href="https://www.huawei.com/br/" target="_blank"
            rel="noreferrer">Huawei</a> internal applications and systems.
        </p>
        <div class="button-row">
          <button class="btn-resume">Resume</button>
        </div>
      </div>
      <!-- <picture class="img">
        <img src="../assets/1658376883882-removebg-preview (1).png" alt="foto pessoal" />
      </picture> -->
    </section>

    <section id="about">
      <About />
    </section>
    <section id="projects">
      <div class="projects-container">
        <Projects />
      </div>
    </section>
    <section id="contact"></section>
  </div>
</template>
<script>
import Projects from "./Projects.vue";
import About from "./About.vue";
export default {
  name: "Home",
  components: {
    Projects: Projects,
    About: About,
  },
  data() {
    return {
      cep: "",
      loading: false,
    };
  },
  methods: {
    searchCep(cep) {
      fetch(`https://viacep.com.br/ws/${cep}/json/`)
        .then((data) => data.json())
        .then((data) => {
          this.loading = false;
          return data;
        });
    },
  },
};
</script>
<style lang="scss">
@import "../assets/scss/main.scss";

* {
  font-family: $font-family1;
  font-weight: 600;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  flex-direction: column;

  a {
    color: $primary-color;
    font-weight: 600;
    text-decoration: none;
    display: inline-block;
    text-decoration-skip-ink: auto;
  }
}

.content-home {
  display: flex;
  gap: 3%;
  min-height: calc(100vh - 100px);

  h1 {
    font-size: 80px;
    line-height: $title-lineh;
    font-weight: 600;
    color: #fff;
  }

  a::after {
    content: "";
    width: 0;
    height: 2px;
    position: absolute;
    bottom: 0.3em;
    right: 0;
    background-color: #950041;
    transition: width 0.25s ease-out;
  }

  a:hover::after {
    color: #950041;
    width: 100%;
    left: 0;
    right: auto;
  }

  button:hover {
    background: rgba(149, 0, 65, 0.4);
  }
}

.text-home {
  display: flex;
  justify-content: center;
  padding: 0 50px;
  flex-direction: column;

  h2 {
    color: $primary-color;
    font-weight: 600;
    margin-bottom: 1.5rem;
  }

  p {
    max-width: 720px;
    color: rgba(255, 255, 255, 0.75);
  }
}

@media screen and (max-width: 900px) {
  img {
    display: none;
  }
}

.img {
  img {
    display: flex;
    border-radius: 50%;
    border: 2px solid #fff;
  }
}

.button-row {
  display: flex;
  justify-content: flex-start;
  margin-top: 4rem;
}

button {
  display: flex;
  width: 300px;
  cursor: pointer;
  border: 2px solid $primary-color;
  border-radius: 4px;
  font-weight: 600;
  font-size: 14px;
  background: transparent;
  color: $primary-color;
  height: 45px;
  align-items: center;
  justify-content: center;
}

// Projects - section
.projects-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}
</style>
