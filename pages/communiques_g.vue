<template>
    <div>
      <Header />
      <PageHeader pageTitle="Communiqués" pageName="Communiqués" />
      <br>
      <br>
      <communiques_display></communiques_display>
      <Footer />
      <MobileDrawer />
    </div>
  </template>
  
  <script >
   import communiques_display from "../components/communiques_display";
  export default {
    components: {communiques_display},
    head(){
      return {
        title: "PFC BENIN | Communiqués"
      }
    }
  }
  </script>
  