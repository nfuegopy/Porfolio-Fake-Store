<template>
  <Menubar :model="menuItems" />
</template>

<script>
import Menubar from 'primevue/menubar';

export default {
  name: 'AppHeader',
  components: {
    Menubar
  },
  data() {
    return {
      menuItems: [
        { label: 'Home', icon: 'pi pi-fw pi-home' },
        { label: 'Productos', icon: 'pi pi-fw pi-list' },
        { label: 'Contacto', icon: 'pi pi-fw pi-phone' }
      ]
    };
  }
};
</script>

<style scoped>
/* Estilos específicos del header */
</style>
