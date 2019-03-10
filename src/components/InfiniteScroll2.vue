<template>
  <div infinite-wrapper>
     <header>Hackers News</header>
      <div v-for="(item, $index) in list" :key="$index">
      </div>
      <infinite-loading @infinite="infiniteHandler"></infinite-loading>
  </div>
</template>
<script>
import InfiniteLoading from 'vue-infinite-loading'; 
import axios from 'axios';

const api = '//hn.algolia.com/api/v1/search_by_date?tags=story';

export default {
  components: {
    InfiniteLoading,
  },
  data() {
    return {
      page: 1,
      list: [],
    };
  },
  methods: {
    infiniteHandler($state) {
      axios.get(api, {
        params: {
          page: this.page,
        },
      }).then(({ data }) => {
        if (data.hits.length) {
          this.page += 1;
          this.list.push(...data.hits);
          // console.log(this.list)
          console.log(this.list.push(...data.hits));
          $state.loaded();
        } else {
          $state.complete();
        }
      });
    },
  },
};
</script>