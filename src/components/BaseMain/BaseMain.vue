<template>
  <main>
      <div class="container">
          <div class="row">
                <CardElement />
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
            album: [],
        };
    },
    components: {
        CardElement,
    },
    created() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then( (response) => {
        // handle success
            this.album = response.data.response; 
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