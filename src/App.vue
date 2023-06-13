<template>
  <main>
    <div ref="count">
      {{ counter }} 
    </div>
    <br>
    <button @click="increase()">Update</button>
  </main>
</template>

<script>

export default {
  data() {
    return {
      counter: 0,
    }
  },
  // START REGISTER LIFECYCLE HOOKS
  beforeCreate() {
    console.log('before create')
  },
  created() {
    console.log('created')
  },
  beforeMount() {
    console.log('before mount')
  },
  async mounted() {
    console.log('mounted')
  },
  beforeUpdate() {
    // akan selalu terpanggil jika terdapat update
    console.log('before update', this.$refs['count'].textContent)
  },
  updated() {
    // akan selalu terpanggil jika terdapat update
    console.log('updated value', this.$refs['count'].textContent)
  },
  // terdapat 2 yang belum teregistrasi yaitu beforeUnmount dan unmounted
  // yang akan kita bahas dalam demo basic component
  // END LIFECYCLE HOOKS
  methods: {
    increase() {
      this.counter++
    }
  }

}

</script>

