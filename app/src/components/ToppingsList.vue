<template>
  <div class="bread">
    <ToppingCard v-for="bread in breads" :key="bread.name" :topping="bread" />
  </div>
  <div class="meat">
    <ToppingCard v-for="meat in meats" :key="meat.name" :topping="meat" />
  </div>
  <div class="cheese">
    <ToppingCard v-for="cheese in cheeses" :key="cheese.name" :topping="cheese" />
  </div>
  <div class="condiment">
    <ToppingCard v-for="condiment in condiments" :key="condiment.name" :topping="condiment" />
  </div>
  <div class="vegetable">
    <ToppingCard v-for="vegetable in vegetables" :key="vegetable.name" :topping="vegetable" />
  </div>
</template>

<script setup>
import ToppingCard from './ToppingCard.vue'

const breads = [
  {
    name: 'Wheat Bread',
    price: 1.5,
    image:
      'https://www.thedailymeal.com/img/gallery/every-subway-bread-option-ranked/wheat-bread-1686235927.webp',
  },
  {
    name: 'White Bread',
    price: 1.5,
    image:
      'https://www.thedailymeal.com/img/gallery/every-subway-bread-option-ranked/white-bread-1686235927.webp',
  },
  {
    name: 'Italian Bread',
    price: 1.5,
    image:
      'https://www.thedailymeal.com/img/gallery/every-subway-bread-option-ranked/italian-herb-cheese-1686235927.webp',
  },
]

const meats = [
  { name: 'Oven Roasted Chicken', price: 3.5 },
  { name: 'Sweet Onion Chicken Teriyaki', price: 3.75 },
  { name: 'Grilled Chicken', price: 3.75 },
  { name: 'Meatballs', price: 3.25 },
  { name: 'Roast Beef', price: 3.75 },
  { name: 'Turkey Breast', price: 3.5 },
  { name: 'Turkey Bacon', price: 4.0 },
  { name: 'Salami', price: 3.25 },
  { name: 'Pepperoni', price: 3.25 },
  { name: 'Bacon', price: 2.5 },
  { name: 'Black Forest Ham', price: 3.25 },
  { name: 'Tuna Salad', price: 3.5 },
  { name: 'Steak', price: 4.5 },
]

const cheeses = [
  { name: 'American Cheese', price: 1.0 },
  { name: 'Cheddar Cheese', price: 1.0 },
  { name: 'Swiss Cheese', price: 1.0 },
  { name: 'Provolone Cheese', price: 1.0 },
  { name: 'Pepperjack Cheese', price: 1.0 },
  { name: 'Mozzarella Cheese', price: 1.0 },
  { name: 'Feta Cheese', price: 1.5 },
]

const condiments = [
  { name: 'Mayonnaise', price: 0.5 },
  { name: 'Mustard', price: 0.5 },
  { name: 'Honey Mustard', price: 0.5 },
  { name: 'Barbecue Sauce', price: 0.5 },
  { name: 'Ranch Dressing', price: 0.5 },
  { name: 'Light Ranch Dressing', price: 0.5 },
  { name: 'Chipotle Southwest Sauce', price: 0.5 },
  { name: 'Vinaigrette', price: 0.5 },
  { name: 'Italian Dressing', price: 0.5 },
  { name: 'Balsamic Vinegar', price: 0.5 },
  { name: 'Ketchup', price: 0.5 },
  { name: 'Buffalo Sauce', price: 0.5 },
  { name: 'Caesar Dressing', price: 0.5 },
]

const vegetables = [
  { name: 'Lettuce', price: 0.75 },
  { name: 'Tomatoes', price: 0.75 },
  { name: 'Cucumbers', price: 0.75 },
  { name: 'Red Onions', price: 0.75 },
  { name: 'Green Peppers', price: 0.75 },
  { name: 'Olives', price: 0.75 },
  { name: 'Spinach', price: 0.75 },
  { name: 'Pickles', price: 0.75 },
  { name: 'Jalapeños', price: 0.75 },
  { name: 'Banana Peppers', price: 0.75 },
  { name: 'Avocado', price: 1.5 },
]
</script>

<style scoped></style>
