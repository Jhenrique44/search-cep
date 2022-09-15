<template>
  <div class="container">
    <section class="content">
      <input type="number" v-model="cep" />
      <button name="search" @click="searchCep(cep)"></button>
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
