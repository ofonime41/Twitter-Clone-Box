<template>
  <div class="container mx-auto">
    <h1 class="text-3xl font-bold text-teal-600 my-2">TWITTER CLONE BOX</h1>
    <div class="w-full md:w-1/2 h-1/2 bg-teal-600  container mx-auto p-10">
      <input  v-model="twitt"  :maxlength="characters"  class="p-4 outline-2 outline-cyan-600"
        type="text" placeholder="Add Twitt" ><br>

      <button class="bg-pink-700 p-2 my-4 w-1/3 shadow-2xl text-white" @click="saveTwitt">Submit</button>
      <div class=" text-black" >
        <p>You have {{remain()}} character(s) left</p>
        
      </div>
    </div>
    <div>


    </div>
    <div class=" container mx-auto w-full md:w-1/2 h-1/2  p-2 bg-teal-200 text-black my-4 text-center" v-for="twitt,id in twitts" :key="id">
      <p class="mx-auto">{{twitt}}</p>
    </div>
  </div>

</template>

<script>


export default {
  name: "App",
  components: {
  },
  data() {
    return {
      twitts: [],
      twitt:'',
      characters:100,

    }
  },
  methods: {
    // Save twitt to an array
    saveTwitt() {
      this.twitts.push(this.twitt);
      this.twitt=''
      
    },

    remain(){
      return this.characters-this.twitt.length
    }
     
    },

};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
 -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #080c0f; */
  margin-top: 10%;
}
</style>
