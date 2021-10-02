<template>
  <section class="quote">
      <div class="quote-content">
          {{quote.content}}
      </div>
      <div class="quote-info">
          <div class="quote-anime">
              Anime: {{quote.anime}}
          </div>
         
         <div class="quote-author">
          Character:{{quote.character}}
        </div>        
      </div>

  </section>
</template>

<script>
export default {
    props: ['quote']
}
</script>
    
<style scoped>
    .quote{
        position: relative;
        margin: 0 auto;
        padding: 32px;
        max-width: 720px;
    }
    .quote-content{
        position: relative;
        font-size: 28px;
        font-weight: 600;
        background-color: #131A26;
        color: #FFF;
        padding: 48px 32px;
        border-radius: 16px;
    }
    .quote-content::before, 
    .quote-content::after{
        content: '"';
        color: #848484;
        margin: 0px 2px;
    } 
    .quote-info{
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        padding: 32px;
    }
    .quote-author, .quote-anime{
        position: absolute;
        padding: 12px 16px;
        font-size: 24px;
        font-weight: 700;
        border-radius: 99px;
        color: #FFF;
        text-align: center;
    }
    .quote-author{
        top: calc(100% - 32px);
        right: 0;
        transform: translateY(-50%);
        background-color: #8A4FFF;
    }
    .quote-anime{
        top: 0;
        left: 0;
        background-color: #32CBFF;
        color: #131A26;
    }
</style>