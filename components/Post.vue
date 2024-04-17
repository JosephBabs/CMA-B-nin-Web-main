<template>
  <div class="news-details__left">
    <div class="news-details__img">
      <img :src="'https://app.cmabenin.bj/web/public/storage/'+thumbnail" alt="" />
    </div> 
    <div class="news-details__content">
      <ul class="list-unstyled news-details__meta">
        <li>
          <a href="#"><i class="far fa-user-circle"></i>{{  author }}</a>
        </li>
        <li><span>/</span></li>
        <li>
          <a href="#"><i class="far fa-comments"></i> {{  commentCount }}</a>
        </li>
      </ul>
      <h3 class="news-details__title">
        {{  title }}
      </h3>
      <!-- <nuxt-content class="news-details__text-one">
        {{  content }}
      </nuxt-content> -->
      <!-- <div v-html=" content" /> -->
      <!-- <p>{{  }}</p> -->
      <p ></p>
      <div class="news-two__text" v-html="content"></div>
      
    </div>
    <div class="news-details__bottom">
      <p class="news-details__tags">
        <span>Tags:</span>
        <a href="#" v-for="item in tags" :key="item.id">{{item.name}}</a>
    
      </p>
      <div class="news-details__social-list">
        <a href="#"><i class="fab fa-twitter"></i></a>
        <a href="#"><i class="fab fa-facebook-square"></i></a>
        <a href="#"><i class="fab fa-dribbble"></i></a>
        <a href="#"><i class="fab fa-instagram"></i></a>
      </div>
    </div>
  </div>
</template>

<script>
import dataT from "~/data/data.json";
export default {
  props: {
    title: {
      type: String,
    },
    author: {
      type: String,
    },
    date: {
      type: String,
    },
    commentCount: {
      type: String,
    },
    thumbnail: {
      type: String,
    },
    excerpt: {
      type: String,
    },
    content: {
      type: String,
    },
    comments: {
      type: String,
    },
    url: {
      type: String,
    },
  },

  data() {
    return {
      // news: [],
      tags: [],
    };
  },

  methods: {
      async getDatas() {
        const apiLink = dataT.apiUrl.link;
        
        const res = await fetch(apiLink+"tags");
        const finalRes = await res.json();
        this.tags = finalRes.tags;
      },
      // formatDate(date) {
      // const options = { year: 'numeric', month: 'long', day: 'numeric' }
      // return new Date(date).toLocaleDateString('en', options)
    // },
  },
  mounted() {
      this.getDatas()
    },
};
</script>
