<template>
    <div>
      <Section>
        <div class="hero-section">
          <h1>Bienvenido a nuestra Galería de Productos</h1>
          <p>Descubre nuestros productos más destacados</p>
          <Button label="Explorar Productos" class="p-button-outlined p-button-rounded" />
        </div>
      </Section>
      <Section>
        <Carousel :value="products" numVisible="3" numScroll="1" class="custom-carousel" :responsiveOptions="responsiveOptions">
          <template v-slot:header>
            <h2>Nuestros Productos</h2>
          </template>
          <template v-slot:item="slotProps">
            <Card>
              <img :src="slotProps.item.image" class="product-image" />
              <div class="p-mt-2">
                <h3>{{ slotProps.item.name }}</h3>
              </div>
            </Card>
          </template>
        </Carousel>
      </Section>
    </div>
  </template>
  
  <script>
  import Section from '@/components/Section.vue';
  import Carousel from 'primevue/carousel';
  import Card from 'primevue/card';
  import Button from 'primevue/button';
  
  import img1 from '@/assets/productoImg/image01.jpg';
  import img2 from '@/assets/productoImg/image02.jpg';
  import img3 from '@/assets/productoImg/image03.jpg';
  import img4 from '@/assets/productoImg/image04.jpg';
  import img5 from '@/assets/productoImg/image05.jpg';
  
  export default {
    name: 'HomePage',
    components: {
      Section,
      Carousel,
      Card,
      Button
    },
    data() {
      return {
        products: [
          { id: 1, name: 'Producto 1', image: img1 },
          { id: 2, name: 'Producto 2', image: img2 },
          { id: 3, name: 'Producto 3', image: img3 },
          { id: 4, name: 'Producto 4', image: img4 },
          { id: 5, name: 'Producto 5', image: img5 }
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
  }
  </style>
  