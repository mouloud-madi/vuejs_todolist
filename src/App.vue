<template>
  <div id="app">
   <Navbar/>
   <Create/>
  </div>
</template>

<script>
import Navbar from './components/layouts/Navbar'
import Create from './components/todos/Create'

export default {
  name: 'App',
  components: {
    Navbar,
    Create,
  }
}
</script>

