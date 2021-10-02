<template>
  <div class='app'>
    <Header title="Anime Quotas"/>
    <Quote :quote="quote"/>
    <div class="button-container">
      <button @click="getQuote">Generate</button>
    </div>
    <QuoteList :quotes="quotes"/>
  </div> 
</template>

<script>
import Header from "./components/Header.vue";
import Quote from "./components/Quote.vue"
import QuoteList from "./components/QuoteList.vue"

export default {
  name: 'App',
  components: {
    Header,
    Quote,
    QuoteList
   },
   data() {
     return {
       quote: {},
       quotes: []
     }
   },
   methods: {
     async getQuote(){
       if(this.quote.content){
         this.quotes = [...this.quotes, this.quote];
       }

       const data = await fetch('https://animechan.vercel.app/api/random').then(res => 
       res.json());

       this.quote = {
         content: data.quote,
         anime: data.anime,
         character: data.character
       }
     }
   },
   created(){
     this.getQuote();
   }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Courier New', Courier, monospace;
  }
  .button-container{
    display: flex;
    justify-content: center;
    padding: 0px 32px;
    margin: 64px auto;
  }
  button{
    border: none;
    outline: none;
    background-color: #D81E5B;
    padding: 16px 32px;
    border-radius: 99px;
    color: #fff;
    cursor: pointer;
    font-size: 28px;
    font-weight: 700;
    text-transform: uppercase;
    transition: 0.4s;
  }
  button:hover{
    background-color: #848484;
  }
</style>

