<script>
export default {
  data() {
    return {
      fact: '',
      loading: false,
    }
  },
  methods: {
    fetchFact() {
      this.loading = true;
      fetch('https://meowfacts.herokuapp.com/')
        .then(response => response.json())
        .then((data) => {
          this.fact = data.data[0];
          this.loading = false;
        })
    }
  }
}
</script>

<template>
  <div>
    <h3>{{ fact }}</h3>
    <button @:click="fetchFact">
      Get a cat fact
    </button>
  </div>
</template>
