<template>
  <div class="countdown">
    <h1>Countdown to our retirement</h1>
    <p class="countdown-text">{{ daysLeft }} days left until retirement</p>
    <p class="countdown-text">{{ weeksLeft }} weeks left until retirement</p>
    <p class="countdown-text">{{ yearsLeft }} years left until retirements</p>
  </div>
</template>

<script>
export default {
  name: 'App',
  mounted() {
    document.title = 'Our retirement page';
  },
  data() {
    return {
      retirementDate: new Date('2027-09-01'),
      currentDate: new Date(),
    }
  },
  computed: {
    daysLeft() {
      const oneDay = 24 * 60 * 60 * 1000; // hours*minutes*seconds*milliseconds
      const diffDays = Math.round(Math.abs((this.retirementDate - this.currentDate) / oneDay));
      return diffDays;
    },
    weeksLeft() {
      const oneWeek = 7 * 24 * 60 * 60 * 1000; // hours*minutes*seconds*milliseconds
      const diffWeeks = Math.round(Math.abs((this.retirementDate - this.currentDate) / oneWeek));
      return diffWeeks;
    },
    yearsLeft() {
      const oneYear = 365 * 24 * 60 * 60 * 1000; // hours*minutes*seconds*milliseconds
      const diffYears = Math.round(Math.abs((this.retirementDate - this.currentDate) / oneYear));
      return diffYears;
    },
  }
}
</script>

<style>
.countdown {
  font-family: Arial, sans-serif;
  text-align: center;
  padding: 20px;
  background-color: #f4f4f4;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.countdown-text {
  font-size: 36px;
  font-weight: bold;
  color: #1c1c1c;
  margin-top: 0;
}
</style>
