<template>
  <div>
    <!--Site Footer One Start-->
    <footer class="site-footer">
      <div
        class="site-footer-bg"
        :style="`background-image: url(${require(`~/assets/images/backgrounds/footer-bg.jpg`)})`"
      ></div>
      <div class="container">
        <div class="site-footer__top">
          <div class="row">
            <div class="col-xl-3 col-lg-6 col-md-6">
              <div class="footer-widget__column footer-widget__about">
                <h3 class="footer-widget__title">Notre Mission</h3>
                <p class="footer-widget__text">
                  La CMA-Bénin a pour mission la représentation, la promotion  du 
              secteur et la protection des intérêts des artisans beninois et des entreprises artisanales auprès 
              des collectivités locales, des instances nationales sous-régionales et internationales.  </p>
                
              </div>
            </div>
            <div class="col-xl-3 col-lg-6 col-md-6">
              <div
                class="footer-widget__column footer-widget__explore clearfix"
              >
                <h3 class="footer-widget__title">Liens rapides</h3>
                <ul class="footer-widget__explore-list list-unstyled">
                  <li><nuxt-link to="/">Accueil</nuxt-link></li>
                  <li><nuxt-link to="/presentation">Présentation</nuxt-link></li>
                  <li><nuxt-link to="/mediateque">Mediatèque</nuxt-link></li>
                  <li><nuxt-link to="/actus">Actualités</nuxt-link></li>
                  <li><nuxt-link to="/documents">Documentst</nuxt-link></li>
                  <li><nuxt-link to="/contact">Contacts</nuxt-link></li>
                </ul>
                
              </div>
            </div>
            <div class="col-xl-3 col-lg-6 col-md-6">
              <div class="footer-widget__column footer-widget__contact">
                <h3 class="footer-widget__title">Contacts</h3>
                <ul class="list-unstyled footer-widget__contact-list">
                  <li>
                    <div class="icon">
                      <i class="icon-chat"></i>
                    </div>
                    <div class="text">
                      <p>
                        <span>Téléphone</span>
                        <a href="tel:+22940687884">+(229) 40 68 78 84</a>
                      </p>
                    </div>
                  </li>
                  <li>
                    <div class="icon">
                      <i class="icon-message"></i>
                    </div>
                    <div class="text">
                      <p>
                        <span>Adresse E-mail</span>
                        <a href="mailto:info@cmabenin.bj"
                          >info@cmabenin.bj</a
                        >
                      </p>
                    </div>
                  </li>
                  <li>
                    <div class="icon">
                      <i class="icon-address"></i>
                    </div>
                    <div class="text">
                      <p><span>Adresse</span>ZONE CEN-SAD/ Quartier Ahwanleko plage, à coté de la commission de l'UEMOA</p>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
            <div class="col-xl-3 col-lg-6 col-md-6">
              <div class="footer-widget__column footer-widget__newsletter">
                <h3 class="footer-widget__title">Newsletter</h3>
                <p class="footer-widget__newsletter-text">
                  Inscrivez-vous à notre newsletter pour être informé de tout.
                </p>
                <form @submit.prevent="submitDat" class="footer-widget__newsletter-form">
                  <input
                      type="email"
                      placeholder="E-mail"
                      name="email"
                      v-model="form.email"
                  />
                  <button type="submit" class="footer-widget__newsletter-btn">
                    <i class="fas fa-arrow-circle-right"></i>Envoyer
                  </button>
                </form>
              </div>
            </div>
          </div>
        </div>
        <div class="site-footer__bottom">
          <div class="row">
            <div class="col-xl-12">
              <div class="site-footer__bottom-inner">
                <div class="site-footer__bottom-logo-social">
                  <div class="site-footer__bottom-logo">
                    <nuxt-link to="/">
                      <img
                        :src="require(`~/assets/images${logo.light}`)" style="width: 220px;"
                        alt=""
                      />
                    </nuxt-link>
                  </div>
                  <!-- <div class="site-footer__bottom-social">
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-facebook-square"></i></a>
                    <a href="#"><i class="fab fa-dribbble"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                  </div> -->
                </div>
                <div class="site-footer__bottom-copy-right">
                  <p>&copy; Copyright {{ new Date().getFullYear() }} | Site réalisé par<a href="#">La Gnose Plus Com</a> | +229 94 44 41 44</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </footer>
    <!--Site Footer One End-->
    <div v-if="sticky === true">
      <a
        @click="scrollTop"
        class="scroll-to-target scroll-to-top animated fadeInUp"
        ><i class="fa fa-angle-up"></i
      ></a>
    </div>
    
    <div class="alert success-a" v-if="showAlert_s">
      Vous avez souscrit à notre newsletter avec succès.</div>

       <div class="alert danger-a" v-if="showAlert_d">
       Erreur: vérifiez votre connexion</div>
  </div>
</template>


<style scope>

/* The alert message box */
.danger-a{
  background-color: #94100B;
  bottom: 10%;
}
.success-a{
  background-color: #0B9438;
  bottom: 10%;
}

.alert {
  padding: 20px;
  color: white;
  position: fixed;
  z-index: 0;
  margin-bottom: 15px;
  margin: 10px;
  display: inline-flex;
  flex-direction: column;
  align-items: last baseline;
  justify-self: center;
}

/* The close button */
.closebtn {
  margin-left: 15px;
  color: white;
  font-weight: bold;
  float: right;
  font-size: 22px;
  line-height: 20px;
  cursor: pointer;
  transition: 0.3s;
}

/* When moving the mouse over the close button */
.closebtn:hover {
  color: black;
}


</style>


<script>

const date = new Date().getFullYear();

import data from "~/data/data.json";

function showAlert(){
  setTimeout(() => {
    const elements = document.getElementsByClassName("alert");
    for (let i = 0; i < elements.length; i++) {
        elements[i].style.display = "none";
    }
}, 3000);

}

async function postData(url, data) {
  try {
    const response = await fetch(url, {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(data),
    });

    if (!response.ok) {
      throw new Error('Network response was not ok');
      alert("Erreur de connexion")
    }

    const result = await response.json();
    return result;
  } catch (error) {
    console.error('Error:', error);
    throw error;
  }
};

export default {
  data() {
    return {
      logo: data.logo,
      sticky: false,
      form: {
          email: "",
        },
      showAlert_s: false, // Initially, hide the alert
      showAlert_d: false, 
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      if (window.scrollY > 70) {
        this.sticky = true;
      } else if (window.scrollY < 70) {
        this.sticky = false;
      }
    },
    scrollTop() {
      window.scrollTo(0, 0);
    },
  },

  async  submitDat() {
  const apiLink = data.apiUrl.link;
  const url = apiLink+'suscribe_newsletter';
  const data = {
    
    email: this.form.email,      
  };

  try {
    const response = await postData(url, data);
    console.log('Response:', response);
    //     this.alertType = 'success';
    // alert("Vous avez souscrit à notre newsletter avec succès.")
    this.showAlert_s = true;
    showAlert()
    this.form.email = "";
    // Handle the response data here
  } catch (error) {
    console.error('Error:', error);
    // alert(" Erreur: Vérifiez votre connexion")
    this.showAlert_d = true;
    showAlert()
    //     this.alertType = 'error';
    //     this.alertMessage = 'vérifiez votre connexion';
    // Handle errors here
  }
},
};
</script>
