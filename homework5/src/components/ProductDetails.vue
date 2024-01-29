<template>
    <div>
      <h1>Магазин горнолыжных товаров</h1>
      <div v-for="item in products" :key="item.id">
        <p> {{ item.id }}</p>
        <p> {{ item.name }}</p>
        <p> {{ formattedPrice(item.price) }}</p>
        <p v-if="item.available">Status: Available</p>
        <p v-else>Status: Out of stock</p>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        products: [
          {
            id: 1,
            name: 'Сноуборд',
            price: 99.99,
            available: true
          },
          {
            id: 2,
            name: 'Лыжи горные',
            price: 59.99,
            available: false
          },
          {
            id: 3,
            name: 'Фигурные коньки',
            price: 39.99,
            available: true
          }
        ]
      };
    },
    methods: {
      formattedPrice(price) {
        const formatter = new Intl.NumberFormat('en-US', {
          style: 'currency',
          currency: 'USD'
        });
        return formatter.format(price);
      }
    }
  };
  </script>
  
  <style lang="scss" scoped>

  </style>