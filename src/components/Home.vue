<template>
  <div class="container">
    <section class="content">

    </section>
    <section id="about">

    </section>
    <section id="projects">

    </section>
    <section id="contact">

    </section>
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
<style>
.container {
  max-width: 1280px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
}
</style>