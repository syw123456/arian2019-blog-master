<template>
    <div class="content media">

      <h1 class="name">Media</h1>
        <div v-for="item in media" :key="item.id">
          <p class="format">{{item.format}}</p>
          <a class="title" :href="item.href" target="_blank">{{item.title}}</a>
          <p class="medium">{{item.medium}}</p>
          <p class="year">{{item.year}}</p>
        </div>

    </div>
</template>
<script>
    import axios from 'axios';
  import data from '../data/media.json'
    export default {
        data() {
            return {
                color: 'blue',
            }
        },
        async asyncData() {
            const res = data;
            // turn object of objects into array of objects, then reverse in order to show media in reverse chronological order
            const media = Object.values(res).reverse();
            return {media};

        },
        components: {
        },
        methods: {
        }

    }


</script>

<style scoped>

.media {
    /*overflow-x: scroll;*/
    height: auto;
    display: flex;
    justify-content: center;
    margin-top: 0px;
    /* max-width: none; */
    max-width: initial;
    margin-bottom: 60px;
    height: 100vh;
}


.title {
  font-size: 1.5em;
  color: #646464;
  word-spacing: -0.04em;
}

.format {
  margin-top: 30px;
  font-size: 1em;
  color: #C3BFBF;
}

.medium {
  font-size: 1.25em;
  color: #9D9D9D;
}

.year {
  color: #553b3b;
  font-size: 0.9em;
  /*margin-bottom: 15px;*/
}

</style>
