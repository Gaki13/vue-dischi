<template>
  <main>
      <div class="container">
          <div class="row">
                <CardElement v-for="album in Albums" :key="album.index" :album="album" class="col-2"/>
          </div>
      </div>
  </main>
</template>

<script>
import CardElement from './CardElement.vue'
import axios from 'axios'
export default {
    name: 'BaseMain',
    data(){
        return{
            Albums: [],
        };
    },
    components: {
        CardElement,
    },
    created() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (response) => {
        // handle success
            this.Albums = response.data.response; 
            console.log(response);
        })
        .catch( (error) => {
        // handle error
            console.log(error);
        });
    }
}
</script>

<style lang="scss" scoped>
    main{
      height: calc(100vh - 6.25rem);  
      background-color: #1e2d3b;
      display: flex;
    }
</style>