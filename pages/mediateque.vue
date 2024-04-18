<template>
  <div>
    <Header />
    <PageHeader pageTitle="Galerie / Video" pageName="Mediatèque" />
    <GalleryGrid />
    <Footer />
    <SearchPopup />
    <MobileDrawer />
  </div>
</template>

<script >
export default {
    
    head(){
      return {
        title: "CMA BENIN| Médiatèque"
      }
    }
  }
</script>
