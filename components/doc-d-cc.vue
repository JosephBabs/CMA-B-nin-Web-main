<template>
    <!--Four Icon Start-->
    <section class="four-icon" id="doc-d-cc">
      <div class="container">
        <div class="row">
          <SectionTitle
              title="Communiqués"
              subTitle="Documents CMA-BENIN"
              alignment="left"
            />
           
            
          
                 <!--Four Icon Single-->
            <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
        

        <!-- Audio Card -->
        

        <div class="pdf-card" v-for="item in tags " :key="item.id"  >
              <h2 class="pdf-title">{{item.version}}</h2>
              <p class="pdf-author">{{item.title}}</p>
              <audio controls class="w-full">
                <source :src="item.audio" type="audio/mp3">
                <!-- Your browser does not support the audio element. -->
            </audio>
            </div>

        <!-- Repeat this card for more audio listings -->

          </div>
        </div>
      </div>
    </section>
    <!--Four Icon End-->
  </template>

  
<script>
import dataT from "~/data/data.json";
const mediaLink = dataT.postImg.link;
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
        const mediaLink = dataT.postImg.link;
        
        const res = await fetch(apiLink+"communique-library");
        // const res = await fetch(apiLink+"video-galleries");
        const finalRes = await res.json();
        this.tags = finalRes.communiques; 
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

  
<style scope>
.pdf-card {
    background-color: #f5f5f5;
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 20px;
    margin-bottom: 20px;
}

.pdf-title {
    font-size: 1.25rem;
    font-weight: bold;
    margin-bottom: 10px;
}

.pdf-author {
    font-size: 1rem;
    color: #888;
}

.pdf-download-button {
    background-color: #11845a;
    color: #fff;
    font-weight: bold;
    padding: 8px 16px;
    border: none;
    border-radius: 999px;
    text-decoration: none;
    display: inline-block;
    transition: background-color 0.3s;
}

.pdf-download-button:hover {
    background-color: #0056b3;
}
</style>
