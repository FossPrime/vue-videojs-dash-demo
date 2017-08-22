<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <video id="example-video" width=600 height=300 class="video-js vjs-default-skin" controls></video>
  </div>
</template>

<script>
import '@/../node_modules/video.js/dist/video-js.css'
import videojs from 'video.js'
import 'dashjs'
import 'videojs-contrib-dash'

export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted () {
    var player = videojs('example-video')

    player.ready(function () {
      player.src({
        src: 'https://dash.akamaized.net/akamai/bbb_30fps/bbb_30fps.mpd',
        type: 'application/dash+xml'
      })

      player.play()
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
