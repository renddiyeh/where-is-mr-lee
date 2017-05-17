<template>
  <div class="counter">
    <h2>{{days}}天 {{pad(hours)}}:{{pad(minutes)}}:{{pad(seconds)}}</h2>
  </div>
</template>

<script>

const startDate = new Date('March 19, 2017 00:00:00');
export default {
  name: 'counter',
  created() {
    this.count();
  },
  methods: {
    pad(n) {
      const str = n.toString();
      if (str.length >= 2) return n;
      return `0${str}`;
    },
    count() {
      const now = new Date();
      // Find the distance between now an the count date
      const distance = now - startDate;
      this.days = Math.floor(distance / (1000 * 60 * 60 * 24));
      this.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      this.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      this.seconds = Math.floor((distance % (1000 * 60)) / 1000);
      setTimeout(this.count, 1000);
    },
  },
  data() {
    return {
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    };
  },

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.counter {
  color: red;
  font-size: 2em;
}

h2 {
  margin-top: 0;
}

</style>
