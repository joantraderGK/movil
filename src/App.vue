//* eslint-disable-next-line no-unsed-vars */
<template class="fondo">
  <div>
    <Navbar />
  <Tarea/>  
  </div>
 
</template>

<script>
import Navbar from './components/Navbar';
import Tarea from './components/Tarea';



export default {
  name: 'App',
  components: {
    Navbar,
    Tarea
  }
}
</script>

<style>

</style>
