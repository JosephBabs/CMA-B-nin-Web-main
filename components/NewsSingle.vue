<template>
  <!--News Details Start-->
  <section class="news-details">
    <div class="container">
      <div class="row">
        <div  class="col-xl-8 col-lg-7"  >
        <div > <Post
                :title="news.title"
                :author="news.author"
                :commentCount="news.comments_count"
                :date="formatDate(news.created_at)"
                :thumbnail="news.cover"
                :excerpt="news.title"
                :content="news.content"
                :url="'/actus-details?post='+news.id"
            
          /></div>
          <!-- <PostAuthor /> -->

          <PostComments  />
<!-- <div class="alert-overlay" v-if="showAlert">
      <Alert
        :type="alertType"
        :message="alertMessage"
        :visible="showAlert"
        @close="hideAlert"
      />
    </div> -->
        </div>
        
        <div class="col-xl-4 col-lg-5">
          <UAlert title="Heads up!" />

          <NewsSidebar />
        </div>
      </div>
    </div>
  </section>
  <!--News Details End-->
</template>
<script>
import Post from "~/components/Post";
import PostAuthor from "~/components/PostAuthor";
import PostComments from "~/components/PostComments";
import NewsSidebar from "~/components/NewsSidebar";
import dataT from "~/data/data.json";
// import Alert from '~/components/alert.vue';


export default {
  components: {
    Post,
    // Alert,
    PostAuthor,
    PostComments,
    NewsSidebar,
  },
  
  data() {
    return {
      news: {},
    };
  },
  methods: {

    reloadPage() {
      location.reload(); // Reload the page
    },

      async getData() {
        const apiLink = dataT.apiUrl.link;
        
        const res = await fetch(apiLink+"posts/"+this.$route.query.post);
        const finalRes = await res.json();
        // console.log(finalRes.post);
        const post = finalRes.post; // Assuming post is an object with properties

        this.news = post;
        if (this.$route.query.post !== this.news.id) {
      const post = await fetchData(this.$route.query.post);
      this.news = post;
    }
// Display specific properties in the alert
      // alert("Post Title: " + post.title);
      },

      
      formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
    }, 
    mounted() {
      this.getData()
      // Attach a click event listener to the <nuxt-link> element
    // const link = this.$el.querySelector('nuxt-link');
    // link.addEventListener('click', this.reloadPage); cma-B-nin-Web-main
    }
};
</script>
