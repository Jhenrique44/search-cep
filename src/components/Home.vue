<template>
  <div class="container">
    <section class="content">
      <div class="text">
        <h2>Hi!!I am</h2>
        <h1>João Henrique.</h1>
        <h2>Front-End Developer.</h2>
        <p>
          I'm a Front-End Developer Intern at Huawei, also a student of computer
          engineering. I'm passionate about learn new things.
        </p>
        <div class="button-row">
          <button class="btn-resume">Resume</button>
        </div>
      </div>
      <picture class="img">
        <img
          src="../assets/1658376883882-removebg-preview (1).png"
          alt="foto pessoal"
        />
      </picture>
    </section>

    <section id="about"></section>
    <section id="projects"></section>
    <section id="contact"></section>
  </div>
</template>
<script>
export default {
  name: "Home",
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
* {
  font-family: "PT Mono", monospace;
}
.container {
  max-width: 1500px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
}
.content {
  display: flex;
  gap: 3%;
  h1 {
    font-size: 80px;
    line-height: 1.1;
    font-weight: 600;
    color: #fff;
  }
}
.text {
  display: flex;
  padding: 0 50px;
  flex-direction: column;
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
  border: 2px solid #fff;
  background: transparent;
  color: #fff;
  height: 45px;
  align-items: center;
  justify-content: center;
}
</style>
