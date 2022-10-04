<template>
<div class="apiMem-field">
  <div class="search-Field">
    <div class="search-Field__button">
      <button type="submit" @click="test">RANDOM</button>
    </div>
    <div class="search-Field__search">
      <input type="search" placeholder="What we looking?" 
       v-model="keyword">
      
    </div>
    <div class="search-Field__button">
      <button type="submit" @click="searchButton">SEARCH</button>
    </div>
  </div>
  <div class="api__img">
    <div class="api__img--picture">
      <img :src="testIMG" id="start">
    </div>
  </div>
</div>

</template>

<script>

export default {

data(){
  return{
    testIMG: ' ',
    keyword: " ",

    
    

  }
},
methods:{
// key = 488b205a6044402f8b084ee7f066771b
// key = c5a6949651ae41e0a44f513db5924261
  test() {
    async function apisyn() {
      let URL = `https://api.humorapi.com/memes/random?keywords=&api-key=c5a6949651ae41e0a44f513db5924261`;
      const res = await fetch(`${URL}`);
      const data = await res.json();
      console.log(data)
      return data
    }
    apisyn().then((test)=>{
      this.testIMG = test.url
    })
    
  },
  searchButton(){
  let testing = this.keyword
  console.log(this.keyword)

  async function apisyn() {
      let URL = `https://api.humorapi.com/memes/random?keywords=${testing}&api-key=c5a6949651ae41e0a44f513db5924261`;
      const res = await fetch(`${URL}`);
      const data = await res.json();
      console.log(data)
      return data
    }
    apisyn().then((test)=>{
      this.testIMG = test.url
    })
}
},
mounted() {
    window.addEventListener('load', () => {
  async function apisyn() {
      let URL = `https://api.humorapi.com/memes/random?keywords=&api-key=c5a6949651ae41e0a44f513db5924261`;
      const res = await fetch(`${URL}`);
      const data = await res.json();
      console.log(data)
      return data
    }
    apisyn().then((test)=>{
      this.testIMG = test.url
    })
    })
},
}
</script>

<style lang="scss">

</style>