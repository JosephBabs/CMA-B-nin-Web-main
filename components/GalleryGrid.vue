<template>
  <section class="gallery-page">
    <div class="container">
      <!-- <div class="row">
        <div
          class="col-xl-4 col-lg-6 col-md-6"
          v-for="item in gallery"
          :key="item.index"
        >
          <GalleryCard
            :title="item.title"
            :thumbnail="item.image"
            :category="item.title"
          />
        </div>
      </div> -->

      <div class="container">
        <section class="gallery" id="galerie">
          <h2>Galerie d'Image</h2>
          <div class="image-list">
            <div
              class="image-item"
              v-for="(item, index) in gallery"
              :key="item.index"
            >
              <img
                :src="item.image"
                class="gallery-image"
                @click="openLightbox(index)"
                :alt="item.title"
              />
            </div>

            <!-- Add more image items as needed -->
          </div>
        </section>
        <div v-if="lightboxVisible" class="lightbox">
          <img
            :src="gallery[currentIndex].image"
            :alt="gallery[currentIndex].title"
            class="lightbox-image"
          />
          <button @click="showPrevious" class="lightbox-nav prev"><i class="fa fa-arrow-left"></i></button>
          <button @click="showNext" class="lightbox-nav next"><i class="fa fa-arrow-right"></i></button>
          <button @click="closeLightbox" class="lightbox-close"><i class="fa fa-times"></i></button>
        </div>

        <section class="gallery" id="video">
          <h2>Galerie Video</h2>
          <div class="video-list">
            <div class="video-item" v-for="item in galleryV"
              :key="item.index">
              <video controls>
                <source :src="item.video" type="video/mp4" />
                Your browser does not support the video tag.
              </video>
            </div>
            
            <!-- Add more video items as needed -->
          </div>
        </section>
      </div>
      <!-- /.row -->
    </div>
    <!-- /.container -->
  </section>
  <!-- /.gallery-page -->
</template>
<script>
import GalleryCard from "~/components/GalleryCard";
import data from "~/data/data.json";
export default {
  components: {
    GalleryCard,
  },
  data() {
    return {
      gallery: [],
      galleryV: [],
      currentIndex: null,
      lightboxVisible: false,
    };
  },
  methods: {
    async getData() {
      const mediaLink = data.postImg.link;
      const apiLink = data.apiUrl.link;
      const res = await fetch(apiLink + "galleries");
      const finalRes = await res.json();
      this.gallery = finalRes.galleries;
    },
    async getData1() {
      const mediaLink = data.postImg.link;
      const apiLink = data.apiUrl.link;
      const res1 = await fetch(apiLink + "video-galleries");
      const finalRes1 = await res1.json();
      this.galleryV = finalRes1.galleries;
    },
    openLightbox(index) {
      this.currentIndex = index;
      this.lightboxVisible = true;
    },
    showPrevious() {
      if (this.currentIndex > 0) {
        this.currentIndex--;
      }
    },
    showNext() {
      if (this.currentIndex < this.gallery.length - 1) {
        this.currentIndex++;
      }
    },
    closeLightbox() {
      this.lightboxVisible = false;
    },
  },
  mounted() {
    this.getData();
    this.getData1();
  },
  watch: {
    currentIndex() {
      if (this.currentIndex !== null) {
        this.currentIndex = Math.max(
          0,
          Math.min(this.currentIndex, this.gallery.length - 1)
        );
      }
    },
  },
};
</script>

<style scope>
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}
.imgG {
  height: 600px;
  overflow: visible;
}

.gallery {
  margin: 20px 0;
}

.gallery h2 {
  font-size: 24px;
  margin: 10px 0;
}

.image-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  width: 100%;
}

.image-item {
  width: 24%; /* Adjust as needed to fit multiple images in a row */
  margin: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  overflow: hidden;
}
@media screen and (max-width: 768px) {
  .image-list {
    flex-direction: column; /* Change to a single column layout */
  }

  .image-item img {
    width: 100%; /* Make images full-width in a single column */
  }
  .image-item {
    width: 100%; /* Make images full-width in a single column */
  }
  
}

.image-item img {
  /* width: 100%;
    height: auto; */
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.video-list {
  display: flex;
  flex-wrap: wrap;
}

.video-item {
  width: 100%;
  height: 100%;
  border: 1px solid #ddd;
  border-radius: 5px;
}
@media screen and (max-width: 768px) {
  .video-list {
    flex-direction: column; /* Change to a single column layout */
  }

  .video-item img {
    width: 100%; /* Make images full-width in a single column */
  }
  .video {
    width: 100%; /* Make images full-width in a single column */
  }
  
}

video {
  width: 100%;
  height: auto;
}

/* Lightbox overlay */
.lightbox {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.7);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 999;
}

/* Lightbox image */
.lightbox-image {
  max-width: 90%;
  max-height: 90%;
  object-fit: contain; /* Adjust this to 'cover' if you want the image to cover the lightbox */
}

/* Lightbox navigation buttons */
.lightbox-nav {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(0, 0, 0, 0.5);
  color: #fff;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 16px;
  transition: background 0.3s;
}

 .prev{
  /* position: absolute; */
  left: 3%;
  
}

 .next{
  /* position: absolute; */
  right: 3%;
}


.lightbox-nav:hover {
  background: rgba(0, 0, 0, 0.7);
}

/* Lightbox close button */
.lightbox-close {
  position: absolute;
  top: 10px;
  right: 10px;
  background: rgba(0, 0, 0, 0.5);
  color: #fff;
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  font-size: 16px;
  transition: background 0.3s;
}

.lightbox-close:hover {
  background: rgba(0, 0, 0, 0.7);
}

</style>
