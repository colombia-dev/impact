<template>
  <div>
    <blockquote>
      <div class="quote">
        {{quote}}
      </div>
      <div class="author">
        {{name}}
        <img :src="avatarUrl" />
      </div>
      <a :href="translateUrl" target="_new">Translate</a>
    </blockquote>
  </div>
</template>

<script>
export default {
  name: 'Quote',
  computed: {
    avatarUrl () {
      return `https://s.gravatar.com/avatar/${this.avatar}?d=https://github.com/colombia-dev/colombia-dev.github.io/raw/master/public/assets/images/simple-logo.png`
    },
    translateUrl () {
      return `https://translate.google.com/?sl=es&tl=en&text=${encodeURIComponent(this.quote)}`
    }
  },
  props: {
    quote: String,
    name: String,
    avatar: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
blockquote {
  background: #f9f9f9;
  border-left: 10px solid #ccc;
  margin: 1.5em 10px;
  font-weight: 300;
  padding: 0.5em 10px;
  quotes: "\201C""\201D""\2018""\2019";
}
blockquote:before {
  color: #ccc;
  content: open-quote;
  font-size: 4em;
  line-height: 0.1em;
  margin-right: 0.25em;
  vertical-align: -0.4em;
}
blockquote p {
  display: inline;
}
.author {
  font-weight: 600;
}
img {
  max-width: 100px;
  max-height: 100px;
}
</style>
