<template>
    <div class="toppings-list">
      <section class="toppings-section">
        <h2>Breads (Choose 1)</h2>
        <div class="toppings">
          <div v-for="bread in breads" :key="bread.name">
            <label>
              <input
                type="radio"
                v-model="selectedBread"
                :value="bread"
              />
              <div class="card">
                <img :src="bread.image" alt="bread.name" />
                <h3>{{ bread.name }}</h3>
                <p>${{ bread.price }}</p>
              </div>
            </label>
          </div>
        </div>
      </section>
  
      <section class="toppings-section">
        <h2>Meats (Max 2)</h2>
        <div class="toppings">
          <div v-for="meat in meats" :key="meat.name">
            <label>
              <input
                type="checkbox"
                :value="meat"
                v-model="selectedMeats"
                :disabled="selectedMeats.length >= 2 && !selectedMeats.includes(meat)"
              />
              <div class="card">
                <img :src="meat.image" alt="meat.name" />
                <h3>{{ meat.name }}</h3>
                <p>${{ meat.price }}</p>
              </div>
            </label>
          </div>
        </div>
      </section>
  
      <section class="toppings-section">
        <h2>Cheeses (Choose 1)</h2>
        <div class="toppings">
          <div v-for="cheese in cheeses" :key="cheese.name">
            <label>
              <input
                type="radio"
                v-model="selectedCheese"
                :value="cheese"
              />
              <div class="card">
                <img :src="cheese.image" alt="cheese.name" />
                <h3>{{ cheese.name }}</h3>
                <p>${{ cheese.price }}</p>
              </div>
            </label>
          </div>
        </div>
      </section>
  
      <section class="toppings-section">
        <h2>Condiments (Unlimited)</h2>
        <div class="toppings">
          <div v-for="condiment in condiments" :key="condiment.name">
            <label>
              <input
                type="checkbox"
                :value="condiment"
                v-model="selectedCondiments"
              />
              <div class="card">
                <img :src="condiment.image" alt="condiment.name" />
                <h3>{{ condiment.name }}</h3>
                <p>${{ condiment.price }}</p>
              </div>
            </label>
          </div>
        </div>
      </section>
  
      <section class="toppings-section">
        <h2>Vegetables (Max 2)</h2>
        <div class="toppings">
          <div v-for="vegetable in vegetables" :key="vegetable.name">
            <label>
              <input
                type="checkbox"
                :value="vegetable"
                v-model="selectedVegetables"
                :disabled="selectedVegetables.length >= 2 && !selectedVegetables.includes(vegetable)"
              />
              <div class="card">
                <img :src="vegetable.image" alt="vegetable.name" />
                <h3>{{ vegetable.name }}</h3>
                <p>${{ vegetable.price }}</p>
              </div>
            </label>
          </div>
        </div>
      </section>
  
      <section class="cart">
  <h2>Your Sandwich</h2>
  <ul>
    <li v-if="selectedBread" >{{ selectedBread?.name }} - ${{ selectedBread?.price }}
      <button @click="removeFromCart('bread')">Remove</button>
    </li>
    <li v-for="(meat, index) in selectedMeats" :key="meat.name">
      {{ meat.name }} - ${{ meat.price }}
      <button @click="removeFromCart('meat', index)">Remove</button>
    </li>
    <li v-if="selectedCheese">{{ selectedCheese?.name }} - ${{ selectedCheese?.price }}
      <button @click="removeFromCart('cheese')">Remove</button>
    </li>
    <li v-for="(condiment, index) in selectedCondiments" :key="condiment.name">
      {{ condiment.name }} - ${{ condiment.price }}
      <button @click="removeFromCart('condiment', index)">Remove</button>
    </li>
    <li v-for="(vegetable, index) in selectedVegetables" :key="vegetable.name">
      {{ vegetable.name }} - ${{ vegetable.price }}
      <button @click="removeFromCart('vegetable', index)">Remove</button>
    </li>
  </ul>
  <h3>Total Price: ${{ totalPrice.toFixed(2) }}</h3>
</section>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  const breads = [
    { name: 'Wheat Bread', price: 1.49, image: 'https://www.thedailymeal.com/img/gallery/every-subway-bread-option-ranked/wheat-bread-1686235927.webp' },
    { name: 'White Bread', price: 1.49, image: 'https://www.thedailymeal.com/img/gallery/every-subway-bread-option-ranked/white-bread-1686235927.webp' },
    { name: 'Italian Bread', price: 1.49, image: 'https://www.thedailymeal.com/img/gallery/every-subway-bread-option-ranked/italian-herb-cheese-1686235927.webp' },
  ];
  
  const meats = [
    { name: 'Oven Roasted Chicken', price: 3.49, image: 'https://cdn.apartmenttherapy.info/image/upload/v1703176803/k/Photo/Recipes/2023-12-how-to-bake-chicken-breasts-in-the-oven/how-to-bake-chicken-breasts-in-the-oven-171-horizontal.jpg' },
    { name: 'Sweet Onion Chicken Teriyaki', price: 3.75, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRlslQhGXALEs66YjDbRtv2fYBb1wdz7jgqxA&s' },
    { name: 'Grilled Chicken', price: 3.75, image: 'https://www.seriouseats.com/thmb/Q9lcFKCESLOEjkll1LmSLx3X7Sw=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/__opt__aboutcom__coeus__resources__content_migration__serious_eats__seriouseats.com__recipes__20150823-grilled-chicken-cutlet-recipe-kenji-08-65180472839e4cf2964dceb188488428.jpg' },
    { name: 'Meatballs', price: 3.25, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTRzQvy_W0gr0Me6i7-V0lQ2HMI2vSkcaVfng&s' },
    { name: 'Roast Beef', price: 3.75, image: 'https://embed.widencdn.net/img/beef/gh6lzohosy/360x360px/Ridiculously%20Tasty%20Roast%20Beef%2002.tif?keep=c&u=7fueml' },
    { name: 'Turkey Breast', price: 3.49, image: 'https://laurenfromscratch.com/wp-content/uploads/2022/09/Sous-vide-cajun-turkey-breast-up-close-featured-image.jpg' },
    { name: 'Salami', price: 3.25, image: 'https://framani.com/cdn/shop/products/Sliced-ItalianDry_1200x1200.jpg?v=1649193184' },
    { name: 'Bacon', price: 2.49, image: 'https://www.rachelcooks.com/wp-content/uploads/2022/04/Air-Fryer-Bacon015-web-square.jpg' },
    { name: 'Black Forest Ham', price: 3.25, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSiLLDA-kguuIdrT70DqOU0E2uRTLd0toE-cQ&s' },
    { name: 'Steak', price: 4.49, image: 'https://cdn.apartmenttherapy.info/image/upload/f_auto,q_auto:eco,c_fill,g_auto,w_1500,ar_3:2/k%2FPhoto%2FSeries%2F2024-04-how-to-cook-a-steak-in-the-oven%2Fhow-to-cook-a-steak-in-the-oven-627' },
  ];
  
  const cheeses = [
    { name: 'American Cheese', price: 0.99, image: 'https://pearlvalleycheese.com/cdn/shop/products/american-sliced-cheese.jpg?v=1676396941' },
    { name: 'Cheddar Cheese', price: 0.99, image: 'https://www.bongards.com/wp-content/uploads/2022/06/6brI8KsOQxunRRPlCqBbRA.jpeg' },
    { name: 'Swiss Cheese', price: 0.99, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRIx4zvQt0-QQyx3cyXlmFoGNqdOLPq_34sZA&s' },
    { name: 'Provolone Cheese', price: 0.99, image: 'https://static.wixstatic.com/media/944b60_9754bd373e6748e696146e5a18262b84~mv2.jpg/v1/fill/w_476,h_476,al_c,q_80,usm_0.66_1.00_0.01,enc_auto/944b60_9754bd373e6748e696146e5a18262b84~mv2.jpg' },
    { name: 'Pepperjack Cheese', price: 0.99, image: 'https://drryor7280ntb.cloudfront.net/media/catalog/product/3/0/30046100328331_1_4ukefwphgjskangg.jpg?width=96&height=96&quality=85&fit=bounds' },
    { name: 'Mozzarella Cheese', price: 0.99, image: 'https://cdn.gardengrocer.com/attachments/photos/high_res/3297.jpg?9976' },
  ];
  
  const condiments = [
    { name: 'Mayonnaise', price: 0.49, image: 'https://cdn.gardengrocer.com/attachments/photos/high_res/4269.jpeg?3275' },
    { name: 'Mustard', price: 0.49, image: 'https://m.media-amazon.com/images/I/71CzSWjX1iL._AC_UF894,1000_QL80_.jpg' },
    { name: 'Honey Mustard', price: 0.49, image: 'https://m.media-amazon.com/images/I/7116qDiMuxS.jpg' },
    { name: 'Barbecue Sauce', price: 0.49, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTY_92KtXVCVMfgyEwfjJXGhCUy-62nzZSqDA&s' },
    { name: 'Ranch Dressing', price: 0.49, image: 'https://images.albertsons-media.com/is/image/ABS/106040071-C1N1?$ng-ecom-pdp-desktop$&defaultImage=Not_Available' },
    { name: 'Chipotle Southwest Sauce', price: 0.49, image: 'https://m.media-amazon.com/images/I/7176rcFDBeL.jpg' },
    { name: 'Ketchup', price: 0.49, image: 'https://i5.walmartimages.com/asr/a75ec13a-c9c8-4f83-95f0-041b40a9c6c1.c8fda2b382a3e2f57382abd05194c07a.jpeg' },
    { name: 'Buffalo Sauce', price: 0.49, image: 'https://m.media-amazon.com/images/I/61qrkVjseAL.jpg' },
  ];
  
  const vegetables = [
    { name: 'Lettuce', price: 0.75, image: 'https://cdn.britannica.com/77/170677-050-F7333D51/lettuce.jpg' },
    { name: 'Tomatoes', price: 0.75, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTN9-OuOtsl4iecwrOQ4c00iOqngoUdBz1dzQ&s' },
    { name: 'Cucumbers', price: 0.75, image: 'https://www.freshpoint.com/wp-content/uploads/2020/02/freshpoint-english-cucumber-scaled.jpg' },
    { name: 'Red Onions', price: 0.75, image: 'https://resources.markon.com/sites/default/files/pi_photos/Onions_Sliced_Red_Hero.jpg' },
    { name: 'Green Peppers', price: 0.75, image: 'https://t3.ftcdn.net/jpg/05/52/90/40/360_F_552904083_VqFFQh0KIRdy6QaK1iumsobDjekhjc84.jpg' },
    { name: 'Pickles', price: 0.75, image: 'https://m.media-amazon.com/images/I/417Ap+kSy5L.jpg' },
    { name: 'Avocado', price: 1.49, image: 'https://popmenucloud.com/cdn-cgi/image/width=1200,height=630,format=auto,fit=cover/twhrnjlo/caf072fd-75a9-4738-b79c-66616f46d1b0.jpg' },
  ];
  
  const selectedBread = ref(null);
  const selectedMeats = ref([]);
  const selectedCheese = ref(null);
  const selectedCondiments = ref([]);
  const selectedVegetables = ref([]);
  
  const totalPrice = computed(() => {
    return (
      (selectedBread.value ? selectedBread.value.price : 0) +
      selectedMeats.value.reduce((total, meat) => total + meat.price, 0) +
      (selectedCheese.value ? selectedCheese.value.price : 0) +
      selectedCondiments.value.reduce((total, condiment) => total + condiment.price, 0) +
      selectedVegetables.value.reduce((total, vegetable) => total + vegetable.price, 0)
    );
  });
  
  const removeFromCart = (type, index = null) => {
    if (type === 'bread') {
      selectedBread.value = null;
    } else if (type === 'meat' && index !== null) {
      selectedMeats.value.splice(index, 1);
    } else if (type === 'cheese') {
      selectedCheese.value = null;
    } else if (type === 'condiment' && index !== null) {
      selectedCondiments.value.splice(index, 1);
    } else if (type === 'vegetable' && index !== null) {
      selectedVegetables.value.splice(index, 1);
    }
  };
  </script>
  
  <style scoped>
  body {
    background-color: #fffeff !important; 
    font-family: 'Oswald', sans-serif;
    color: #231f20 !important; 
}

h1, h2, h3 {
  font-family: 'Oswald', sans-serif;
}

.cart h3 {
  font-family: 'Oswald', sans-serif;
  font-weight: 700; 
}

.toppings-list {
  max-width: 900px;
  margin: 0 auto;
  margin-right: -75%;
}

.toppings-section {
  margin: 20px 0;
  margin-top: 10%;
}

h2 {
    font-size: 2rem;
    text-align: center;
}

.toppings {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.card {
  text-align: center;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 8px;
  width: 180px;
  background-color: #fff;
}

.card img {
  width: 100%;
  height: 100px;
  object-fit: cover;
}

.card h3 {
  margin: 10px 0;
  font-size: 1.5rem;
  color: #ffffff;
}

.card p {
  font-size: 1.3rem;
  color: #ffffff;
  font-family: 'Raleway', sans-serif;
}

.card {
  background-color: #169f51;
  color: #fff;
  border: none;
  padding: 5px 10px;
  border-radius: 5px;
  cursor: pointer;
}

.card:hover {
  background-color: rgb(20, 150, 85); 
  scale: 1.1;
  transition: 0.5s;
}

.cart {
  margin-top: 30px;
  background-color: #231f20 ;
  color: #fff ;
  padding: 20px;
  border-radius: 8px;
  margin-bottom: 80px;
}

.cart h3 {
  font-size: 1.5rem;
  font-weight: bold;
  color: #f6df31 
}

.cart button {
  background-color: #ef4d4d ;
  font-family: 'Oswald';
  width: 70px;
  margin-left: 5%;
}

.cart button:hover {
  background-color: #ff3535 ;
scale: 1.1;
transition: 0.5s;
}
  </style>
  