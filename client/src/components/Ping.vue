<template>
  <div class="container">
    <p>{{ msg }}</p>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: 'Ping',
  data() {
    return {
      msg: 'Hello',
    };
  },
  methods: {
    getMessage() {
      const path = 'http://localhost:5000/ping';

      axios.get(path).then((res) => {
        this.msg = res.data;
      }).catch((error) => console.error(error));

      // fetch(path).then(response => response.json())
      //   .then(json => {
      //     this.msg = json.data;
      //   });
    },
  },
  created() {
    this.getMessage();
  },
};
</script>
