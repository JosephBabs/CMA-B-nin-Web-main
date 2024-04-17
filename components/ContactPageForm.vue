<template>
  <!--Contact page Start-->
  <section class="contact-page">
    <div class="container">
      <div class="section-title text-center">
        <span class="section-title__tagline">Contactez-nous</span>
        <h2 class="section-title__title">
          Pour plus de renseignements <br />
          
        </h2>
      </div>
      <div class="row">
        <div class="col-xl-6 col-lg-6">
          <div class="contact-page__left">
            <div class="contact-page__img">
              <img src="~images/resources/contact-page-img-1.jpg" alt="" />
            </div>
            <p class="contact-page__text">
              La CMA-Bénin a pour mission la représentation, la promotion  du 
              secteur et la protection des intérêts des artisans beninois et des entreprises artisanales auprès 
              des collectivités locales, des instances nationales sous-régionales et internationales.
            </p>
            <div class="contact-page__contact-info">
              <ul class="contact-page__contact-list list-unstyled">
                <li>
                  <div class="icon">
                    <span class="icon-chat"></span>
                  </div>
                  <div class="text">
                    <p>Téléphone</p>
                    <a href="tel:+22940687884">+(229) 40 68 78 84</a>
                  </div>
                </li>
                <li>
                  <div class="icon">
                    <span class="icon-message"></span>
                  </div>
                  <div class="text">
                    <p>Adresse E-mail</p>
                    <a href="mailto:info@cmabenin.bj"
                      >info@cmabenin.bj</a
                    >
                  </div>
                </li>
                <li>
                  <div class="icon">
                    <span class="icon-address"></span>
                  </div>
                  <div class="text">
                    <p>Adresse</p>
                    <h5>ZONE CEN-SAD/ Quartier Ahwanleko plage, à coté de la commission de l'UEMOA</h5>
                  </div>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="col-xl-6 col-lg-6">
          <div class="contact-page__form">
            <form
            @submit.prevent="submitData"
              class="contact-page__main-form contact-form-validated"
            >
              <div class="row">
                <div class="col-xl-12">
                  <div class="contact-page__input-box">
                    <input type="text" placeholder="Nom et prénom"
                      v-model="form.fullname" name="name" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-xl-6">
                  <div class="contact-page__input-box">
                    <input
                      type="email"
                      placeholder="Adresse E-mail"
                      name="email"
                      v-model="form.email"
                    />
                  </div>
                </div>
                <div class="col-xl-6">
                  <div class="contact-page__input-box">
                    <input type="text" placeholder="Objet" name="subject" v-model="form.object" />
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-xl-12">
                  <div class="contact-page__input-box">
                    <input
                      type="text"
                      placeholder="Numéro de téléphon ex: +229000000000"
                      name="phone"
                      v-model="form.phoneNumber"
                    />
                  </div>
                </div>
                <div class="col-xl-12">
                  <div class="contact-page__input-box">
                    <textarea
                      v-model="form.message"
                      name="message"
                      placeholder="Saisissez votre message ici"
                    ></textarea>
                  </div>
                  <button type="submit" class="thm-btn contact-page__btn">
                    <i class="fas fa-arrow-circle-right"></i>Envoyer un message
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
    <div class="alert success-a" v-if="showAlert_s">
       Message envoyé avec succès</div>

       <div class="alert danger-a" v-if="showAlert_d">
       Erreur: vérifiez votre connexion</div>
      
  </section>
  
  <!--Contact page End-->
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

import dataT from "~/data/data.json";
import Alert from '~/components/alert.vue';

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

export default{
  
  data() {
    return {
      form: {
          
          fullname: "", 
          email: "",
          phoneNumber: "",
          object: "",
          message: "",
        },
        showAlert_s: false, // Initially, hide the alert
      showAlert_d: false, 
        alertType: '',    // Type of the alert ('success' or 'error')
      alertMessage: '', // Message to display in the alert
    
    }
  },
  name: 'ContactForm',

  methods: {
    
      
      async  submitData() {
          const apiLink = dataT.apiUrl.link;
          const url = apiLink+'contacts';
          const data = {
    

          fullname: this.form.fullname, 
          email: this.form.email,
          phoneNumber: this.form.phoneNumber,
          object: this.form.object,
          message: this.form.message,
          
  };

  try {
    const response = await postData(url, data);
    console.log('Response:', response);
    // alert("Votre message a été envoyé avec succès")

    this.showAlert_s = true;
    showAlert()
    // this.showAlert = true;
    //     this.alertType = 'success';
    //     this.alertMessage = 'Message envoyé';
    // // Handle the response data here
  } catch (error) {
    console.error('Error:', error);
    this.showAlert_d = true;
    showAlert()
    // alert("Erreur: une erreur s'est produite\n; vérifiez votre connexion")
    // this.showAlert = true;
    //     this.alertType = 'error';

    //     this.alertMessage = 'vérifiez votre connexion';
    // // Handle errors here
  }
},

  }
}
</script>
