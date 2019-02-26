<template>
  <ul class="payment__list">
    <li
      class="payment__item"
      v-for="(payment, index) in payments"
      :key="index">
        <template v-if="payment.currencyType === currency">
          <span>Price:</span> {{ payment.price }} {{ payment.currencyType }}
          <span>Payee:</span> {{ payment.payee }}
        </template>
      </li>
  </ul>
</template>
<script>
export default {
  name: 'PaymentList',
  props: {
    currency: {
      type: String,
      default: 'USD',
    },
  },
  data() {
    return {
      payments: [
        {
          name: 'Cookies', price: 3.00, currencyType: 'USD', payee: 'Platzi Commerce',
        },
        {
          name: 'Soda', price: 4.00, currencyType: 'MXN', payee: 'Platzi Commerce',
        },
        {
          name: 'Cookies', price: 3.00, currencyType: 'USD', payee: 'Platzi Commerce',
        },
        {
          name: 'Chocolate Cookies', price: 5.00, currencyType: 'COP', payee: 'Platzi Commerce',
        },
        {
          name: 'Ice Cream', price: 6.00, currencyType: 'COP', payee: 'Platzi Commerce',
        },
      ],
    };
  },
};
</script>

<style scoped>
.payment__list > .payment__item {
  list-style: none;
  padding: 5px 0;
}

.payment__list > .payment__item span {
  font-weight: bold;
  text-transform: uppercase;
}
</style>
