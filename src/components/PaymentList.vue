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
  render() {
    const filteredPayments = this.payments
      .filter(payment => payment.currencyType === this.currency)
      .map(payment => <li class="payment__item">
        <span>Price: </span> {payment.price} {payment.currencyType}
        <span>Payee: </span> {payment.payee}
      </li>);

    return <ul class="payment__list">
      {filteredPayments}
    </ul>;
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
