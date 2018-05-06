  <template>
    <h1>music</h1>
  </template>


  <script>
    import store from '@/vuex/store'
    export default({
      store,
      created(){
        this.$store.commit('routeLinks',{
          color:"green",
          title:"music",
        });
      }
    })
  </script>

  <style scoped>

  </style>
