<template>
  <div class="home">
    <div class="display-4 ma-4 d-flex justify-center">
      All Videos
    </div>
    
    <VideoTable :videos="videos" :headers="headers" />
  </div>
</template>

<script>
import { mapState } from 'vuex';
import VideoTable from '@/components/VideoTable'

export default {
  components: {
    VideoTable
  },
  computed: {
    ...mapState({
      videos: state => state.videos.videos
    }),
    headers(){
      return [
        {text: 'Played', value: 'played', sortable: false, width: "70px"},
        {text: 'Name', value: 'name'},
        {text: 'Date', value: 'sortable_published_at'},
        {text: 'Duration', value: 'duration'},
        {text: 'Tags', value: 'tags', sortable: false},
      ]
    },
  }
}
</script>

<style>
</style>
