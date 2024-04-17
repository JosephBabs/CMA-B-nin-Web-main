<template>
  <div class="sidebar">
    <div class="sidebar__single sidebar__search">
      <form action="#" class="sidebar__search-form">
        <input type="search" placeholder="Rechercher" />
        <button type="submit"><i class="icon-magnifying-glass"></i></button>
      </form>
    </div>
    <div class="sidebar__single sidebar__post">
      <h3 class="sidebar__title">Recent Posts</h3>
      <ul class="sidebar__post-list list-unstyled">
        <li v-for="card in news" :key="card.id">
          <div class="sidebar__post-image" >
            <img :src="'https://app.cmabenin.bj/web/public/storage/'+card.cover" alt="" />
          </div>
          <div class="sidebar__post-content">
            <h3>
              <a href="#" class="sidebar__post-content_meta"
                ><i class="far fa-user-circle"></i>par {{card.author}}</a
              >
              <nuxt-link  :to="'/actus-details?post='+card.id" :key="card.id"
               ><a target="_blank">{{ card.title }}</a></nuxt-link
              >
            </h3>
          </div>
        </li>
      </ul>
    </div>
    <div class="sidebar__single sidebar__category">
      <h3 class="sidebar__title">Catégories</h3>
      <ul class="sidebar__category-list list-unstyled">
        <!-- <li>
          <a href="#"><i class="fas fa-arrow-circle-right"></i>Charity</a>
        </li> -->
      </ul>
    </div>
    <div class="sidebar__single sidebar__tags">
      <h3 class="sidebar__title">Les Tags</h3>
      <div class="sidebar__tags-list">
        <a href="#" v-for="item in tags" :key="item.id">{{item.name}}</a>
      </div>
    </div>
  </div>
</template>

<script>

import dataT from "~/data/data.json";
export default {  
  data() {
    return {
      news: [],
      tags: [],
    };
  },
 
  methods: {
      async getData() {
        const apiLink = dataT.apiUrl.link;
        
        const res = await fetch(apiLink+"posts");
        const finalRes = await res.json();
        this.news = finalRes.posts;
      },
      formatDate(date) {
      const options = { year: 'numeric', month: 'long', day: 'numeric' }
      return new Date(date).toLocaleDateString('en', options)
    },

    async getData1() {
        const apiLink = dataT.apiUrl.link;
        
        const res = await fetch(apiLink+"tags");
        const finalRes = await res.json();
        this.tags = finalRes.tags;
      },

      // async getData2() {
      //   const apiLink = dataT.apiUrl.link;
      //   const res = await fetch(apiLink+"CategoryPosts");
      //   const finalRes = await res.json();
      //   this.tags = finalRes.tags;
      // },
      
    },
    mounted() {
      this.getData()
      this.getData1()
      // this.getData2()
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
