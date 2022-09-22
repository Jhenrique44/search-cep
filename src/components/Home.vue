<template>
  <div class="container">
    <section id="Home" class="content">
      <div class="text">
        <h2>Hi, my name is</h2>
        <h1>João Henrique.</h1>
        <h2>Front-End Developer.</h2>
        <p>
          I'm a Front-End developer intern at Huawei, I'm also a student of Computer Engineering. I have been working
          with VueJs, utilizing HTML5 CSS3 and JavaScript to build Huawei internal applications and systems.
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
}

.container {
  max-width: 1280px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

.content {
  display: flex;
  gap: 3%;
  min-height: calc(100vh - 100px);

  h1 {
    font-size: 80px;
    line-height: $title-lineh;
    font-weight: 600;
    color: #fff;
  }
}

.text {
  display: flex;
  // margin-top: 150px;
  justify-content: center;
  padding: 0 50px;
  flex-direction: column;

  h2 {
    color: rgba(255, 255, 255, 0.95);
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
  margin-top: 2rem;
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
