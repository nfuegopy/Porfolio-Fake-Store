<template>
  <div>
    <BaseSection>
      <div class="hero-section">
        <h1>Bienvenido a nuestra Galería de Productos</h1>
        <p>Descubre nuestros productos más destacados</p>
        <Button label="Explorar Productos" class="p-button-outlined p-button-rounded" />
      </div>
    </BaseSection>
    <BaseSection>
      <Carousel :value="products" :numVisible="3" :numScroll="1" class="custom-carousel" :responsiveOptions="responsiveOptions">
        <template v-slot:header>
          <h2>Nuestros Productos</h2>
        </template>
        <template v-slot:item="slotProps">
          <Card>
            <img :src="slotProps.item.image" class="product-image" alt="Product Image" />
            <div class="p-mt-2">
              <h3>{{ slotProps.item.name }}</h3>
            </div>
          </Card>
        </template>
      </Carousel>
    </BaseSection>
  </div>
</template>

<script>
import BaseSection from '@/components/BaseSection.vue';
import Carousel from 'primevue/carousel';
import Card from 'primevue/card';
import Button from 'primevue/button';

export default {
  name: 'HomePage',
  components: {
    BaseSection,
    Carousel,
    Card,
    Button
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Producto 1', image: 'https://via.placeholder.com/300x300.png?text=Producto+1' },
        { id: 2, name: 'Producto 2', image: 'https://via.placeholder.com/300x300.png?text=Producto+2' },
        { id: 3, name: 'Producto 3', image: 'https://via.placeholder.com/300x300.png?text=Producto+3' },
        { id: 4, name: 'Producto 4', image: 'https://via.placeholder.com/300x300.png?text=Producto+4' },
        { id: 5, name: 'Producto 5', image: 'https://via.placeholder.com/300x300.png?text=Producto+5' }
      ],
      responsiveOptions: [
        {
          breakpoint: '1024px',
          numVisible: 3,
          numScroll: 1
        },
        {
          breakpoint: '768px',
          numVisible: 2,
          numScroll: 1
        },
        {
          breakpoint: '560px',
          numVisible: 1,
          numScroll: 1
        }
      ]
    };
  }
};
</script>

<style scoped>
.hero-section {
  text-align: center;
  padding: 2rem 0;
  background: url('https://via.placeholder.com/1920x600.png?text=Hero+Background') no-repeat center center;
  background-size: cover;
  color: white;
}

.hero-section h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.hero-section p {
  font-size: 1.5rem;
  margin-bottom: 2rem;
}

.custom-carousel .product-image {
  width: 100%;
  height: auto;
  display: block;
  margin: auto;
}
</style>
