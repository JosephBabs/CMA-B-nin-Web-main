<template>
  <!--News Page Start-->
  <section class="news-page">
    <div class="container">
      <SectionTitle
        title="Actualités"
        subTitle="CMA-Bénin"
      />
      <div class="row">
        <div v-for="card in news" :key="card.index" class="col-xl-4 col-lg-4">
          <u-animate-container>
            <u-animate
              name="fadeInUp"
              :delay="`${card.index + 0}00ms`"
              duration="1500ms"
              :iteration="1"
              :offset="0"
              animateClass="animated"
              :begin="false"
            >
              <NewsCard
                :title="card.title"
                :author="card.author"
                :commentCount="card.comments_count"
                :date="formatDate(card.created_at)"
                :thumbnail="card.cover"
                :excerpt="card.content.substring(0, 100) +'...'"
                :url="'/actus-details?post='+card.id"
              />
            </u-animate>
          </u-animate-container>
        </div>
      </div>
    </div>
  </section>
  <!--News Page End-->
</template>
<script>
import { UAnimateContainer, UAnimate } from "vue-wow";
import NewsCard from "~/components/NewsCard";
import data from "~/data/data.json";
export default {
  components: {
    NewsCard,
    UAnimateContainer,
    UAnimate,
  },
  
  data() {
    return {
      news: [],
    };
  },
 
  methods: {
      async getData() {
        const apiLink = data.apiUrl.link;
        
        const res = await fetch(apiLink+"posts");
        const finalRes = await res.json();
        this.news = finalRes.posts;
      },
      formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    }
    },
    mounted() {
      this.getData()
    },
    computed: {
    truncatedDescription() {
      if (this.card.content) {
        // Truncate the description to the first 100 characters
        return this.card.content.substring(0, 100);
      }
      // If the description is empty, you can provide a default value or handle it accordingly
      return "No description available";
    }
  }

};
</script>
