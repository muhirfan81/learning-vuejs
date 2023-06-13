<template>
  <main>
    <!-- Bentuk paling dasar dari pengikatan data adalah interpolasi 
    teks menggunakan sintaks "Mustache" (kurung kurawal ganda) -->
    {{ msg }}

    <br>
    <!-- "Mustache" tidak dapat digunakan di dalam atribut HTML 
    untuk itu gunakan v-bind atau cukup dengan :[attribute] -->
    <button v-bind:disabled="isDisabledButton" @click="changeMsg()">Attibute Bind v-bind!</button>
    or
    <button :disabled="isDisabledButton" @click="changeMsg()">Attibute Bind Shorthand!</button>
  </main>
</template>

<script>

export default {
  data() {
    return {
      msg: "Hallo world",
      isDisabledButton: true
    }
  },
  methods: {
    changeMsg() {
      // value msg akan berganti secara REAKTIF. saat terjadi perubahan tampilan juga diperbarui
      this.msg = "Hi! My Name Is ...."
    }
  }
}

</script>


<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
