<template>
    <div>
        <div v-for="product in products" :key="product.id">
            <h2> {{ product.name }}</h2>
            <span> цена: {{ formattedPrice(product.price) }}</span>

            <div v-if="product.available">
                <span> Availeble</span>
            </div>
            <div v-else>
                <span> Out of stock</span>
            </div>
            <br>
        </div>
    </div>
</template>

<script>
export default {
  name: 'ProductDetails',

  data () {
    return {
      moneta: '',
      products: [
        {
          id: 1,
          name: 'duster',
          price: '13.99',
          available: true
        },
        {
          id: 2,
          name: 'tv',
          price: '99.99',
          available: true
        },
        {
          id: 3,
          name: 'phone',
          price: '50',
          available: false
        },
        {
          id: 4,
          name: 'camera',
          price: '25.50',
          available: true
        }
      ]
    }
  },
  computed: {
    formattedPrice () {
      return price => `$ ${price}`
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
