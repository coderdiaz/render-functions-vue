<template>
  <div id="app">
    <ul class="filter__list">
      <li class="filter__item"><a @click.prevent="changeFilter('USD')" href="#">USD</a></li>
      <li class="filter__item"><a @click.prevent="changeFilter('MXN')" href="#">MXN</a></li>
      <li class="filter__item"><a @click.prevent="changeFilter('COP')" href="#">COP</a></li>
    </ul>
    <PaymentList :currency="currency"></PaymentList>
  </div>
</template>

<script>
import PaymentList from '@/components/PaymentList.vue';

export default {
  name: 'app',
  data() {
    return {
      currency: 'USD',
    };
  },
  methods: {
    changeFilter(type) {
      this.currency = type;
    },
  },
  components: {
    PaymentList,
  },
};
</script>

<style>
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  text-align: center;
}

.filter__list > .filter__item {
  list-style: none;
  padding: 5px 0;
  display: inline-flex;
  margin-right: 10px;
}

.filter__list > .filter__item a {
  text-decoration: none;
  color: #1e2fbb;
  font-weight: bold;
}
</style>
