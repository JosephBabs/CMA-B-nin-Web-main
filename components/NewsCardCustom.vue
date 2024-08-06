<template>
    <!--News Two Single-->
    <div class="news-two__single">
      <div class="news-two__img-box">
        <div class="news-two__img">
          <img src="https://app.cmabenin.bj/web/public/storage/cover/ZuDSqP7Bm1pPAsMRdJQVxWBqfh3oH0Zt0aqvsaK6.jpg" :alt="title" />
          <a href="https://shorturl.at/2MRAH" target="_blank">
            Clickez Pour télécharger
          </a>
        </div>
        <div class="news-two__date">
          <p>26-06-2024</p>
        </div>
      </div>
      <div class="news-two__content">
        <ul class="list-unstyled news-two__meta">
          <li>
            <a href="#"><i class="far fa-file"></i> PDF</a>
          </li>
          <li><span></span></li>
          <li>
            
          </li>
        </ul>
        <h3>
          <a href="https://shorturl.at/2MRAH" target="_blank" > Questionnaires de sélection des oeuvres innovantes</a>
          
        </h3>
        <a href="https://shorturl.at/2MRAH" target="_blank" class="btn btn-primary btn-lg" >Télécharger le questionnaire</a>
      </div>
    </div>
  </template>
  
  <script>
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
      url: {
        type: String,
      },
    },
  };
  </script>
  