<template>
  <section class="quote-list">
      <div class="quote" v-for="(quote, i) in quotes.slice().reverse()" :key="i">
          <div class="quote-content">
              {{quote.content}} <i class="fas fa-trash-alt" id="delete" @click="deleteFromQuote(i)"></i>
          </div>
      </div>
  </section>
</template>

<script>
export default {
    props: ['quotes'],
    methods: {
        deleteFromQuote(i){
            this.quotes.splice(i, 1)
        }
    },
}
</script>

<style scoped>
    .quote-list{
        padding: 32px;
        max-width: 720px;
        margin: 0 auto;
    }

    #delete{
        color: rgb(252, 0, 0);
        font-size: 16px;
    }
    .quote{
        background-color: #FFF;
        padding: 16px;
        border-radius: 16px;
        margin-bottom: 16px;
    }
    .quote-content{
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
        line-height: 18px;
        max-height: 10px;
    }

    .quote-content:hover{
        white-space: unset;
        max-height: unset;
    }
</style>