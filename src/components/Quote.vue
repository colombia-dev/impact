<template>
  <figure class="snip1359">
  <figcaption><img :src="avatarUrl" class="profile"/>
    <blockquote>{{quote}}</blockquote>
     <a :href="translateUrl" target="_new">Translate</a>
  </figcaption>
  <h3>{{name}}</h3>
</figure>
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
@import url(https://fonts.googleapis.com/css?family=Roboto:300,400);
@import url(https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css);
.snip1359 {
  font-family: sans-serif;
  position: relative;
  float: left;
  overflow: hidden;
  margin: 10px 6%;
  min-width: 230px;
  max-width: 920px;
  width: 100%;
  color: #ffffff;
  text-align: left;
  line-height: 1.4em;
  background-color: #f4ae62;
  padding-top: 120px;
  border-radius: 16px;
}
.snip1359 * {
  -webkit-box-sizing: border-box;
  box-sizing: border-box;
}
.snip1359 img {
  max-width: 100%;
  vertical-align: top;
  opacity: 0.85;
}
.snip1359 figcaption {
  width: 100%;
  background-color: #350f0f;
  padding: 25px;
  position: relative;
}
.snip1359 figcaption:before {
  position: absolute;
  content: '';
  bottom: 100%;
  left: 0;
  width: 0;
  height: 0;
  border-style: solid;
  border-width: 55px 0 0 400px;
  border-color: transparent transparent transparent #00000061;
}
.snip1359 .profile {
  border-radius: 50%;
  position: absolute;
  bottom: 100%;
  left: 25px;
  z-index: 1;
  max-width: 90px;
  opacity: 1;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
}
.snip1359 h3 {
  font-size: 1.3em;
  margin: 25px;
  font-weight: 300;
  position: absolute;
  top: 0;
  right: 0;
  text-align: right;
  color: #fff;
  font-weight: 900;
}
.snip1359 h3 span {
  display: block;
  font-size: 0.65em;
  color: #2980b9;
}
.snip1359 blockquote {
  margin: 0 0 10px;
  padding: 0 0 30px;
  letter-spacing: 1px;
  opacity: 0.8;
  font-style: italic;
  font-weight: 300;
}
.snip1359 blockquote:after {
  font-family: 'FontAwesome';
  content: "\201C";
  position: absolute;
  font-size: 180px;
  line-height: 1em;
  color: #754524;
  font-style: normal;
  content: "\201D";
  bottom: -87px;
  right: 13px;
}

a:link,a:visited,a:hover,a:active {
    color: #754524;
    margin-left: 82%;
}

body {
  background-color: #212121;
}

</style>
