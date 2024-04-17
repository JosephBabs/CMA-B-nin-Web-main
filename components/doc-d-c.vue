<template>
  <!--Four Icon Start-->
  <section class="four-icon" id="doc-d-c">
    <div class="container">
      <div class="row">
        <SectionTitle title="Loi, Décrets et Arrêtés" subTitle="CMA-BENIN" alignment="left" />
        <!-- <audio width="320" height="240" controls="" v-for="item in tags " :key="item.id">
                        <source :src="mediaLink+ '/storage/AudioLib/hdXveOZDU6wlbiyvsREAPNbhqIPj9sokdCqiSDPb.mp3'" type="audio/mpeg">
                         <source src="/storage/AudioLib/hdXveOZDU6wlbiyvsREAPNbhqIPj9sokdCqiSDPb.mp3" type="audio/ogg"> -->
        <!-- Votre navigateur n'accepte pas les tags audios.
                    </audio>  -->
        <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
          <div class="pdf-card">
            <h2 class="pdf-title">
              ARRETES INTERMINISTERIELS - CQM
            </h2>
            <p class="pdf-author">Par : Super Admin</p>
            <a href="https://app.cmabenin.bj/web/public/docs/ARRETES INTERMINISTERIELS - CQM.pdf"
              class="pdf-download-button">Télécharger PDF</a>
          </div>
        </div>

        <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
          <div class="pdf-card">
            <h2 class="pdf-title">
              Code communautaire de l'artisanat (UEMOA)
            </h2>
            <p class="pdf-author">Par : Super Admin</p>
            <a href="https://app.cmabenin.bj/web/public/docs/Code communautaire de l'artisanat (UEMOA).pdf"
              class="pdf-download-button">Télécharger PDF</a>
          </div>
        </div>


        <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
          <div class="pdf-card">
            <h2 class="pdf-title">
              Decret-2022-389 - CERTIFICATIONS FORMATIONS PROFESSIONNELLES
            </h2>
            <p class="pdf-author">Par : Super Admin</p>
            <a href="https://app.cmabenin.bj/web/public/docs/decret-2022-389 - CERTIFICATIONS FORMATIONS PROFESSIONNELLES.pdf"
              class="pdf-download-button">Télécharger PDF</a>
          </div>
        </div>

        <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
          <div class="pdf-card">
            <h2 class="pdf-title">
              Loi-2020-24 du 02 septembre portant création CMA-BENIN
            </h2>
            <p class="pdf-author">Par : Super Admin</p>
            <a href="https://app.cmabenin.bj/web/public/docs/loi-2020-24 du 02 septembre portant création CMA-BENIN.pdf"
              class="pdf-download-button">Télécharger PDF</a>
          </div>
        </div>








        <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
          <div class="pdf-card">
            <h2 class="pdf-title">
              DECRET N° 2021-271 DU 02 JUIN 2021 statuts de la CMA-BENIN
            </h2>
            <p class="pdf-author">Par : Super Admin</p>
            <a href="https://app.cmabenin.bj/web/public/docs/DECRET N° 2021-271 DU 02 JUIN 2021 statuts de la CMA-BENIN.pdf"
              class="pdf-download-button">Télécharger PDF</a>
          </div>
        </div>

        <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
          <div class="pdf-card">
            <h2 class="pdf-title">DECRET_2022-330_-_JAB[1]</h2>
            <p class="pdf-author">Par : Super Admin</p>
            <a href="https://app.cmabenin.bj/web/public/storage/docs/DECRET_2022-330_-_JAB[1].pdf"
              class="pdf-download-button">Télécharger PDF</a>
          </div>
          <!--Four Icon Single-->
        </div>
        <!--Four Icon Single-->
        <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
          <!-- Audio Card -->

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

      const res = await fetch(apiLink + "communique-library");
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
    this.getDatas();
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
