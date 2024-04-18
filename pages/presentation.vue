<template>
  <div>
    <Header />
    <PageHeader pageTitle="Présentation" pageName="Présentation" />
    <AboutOne />
    <CausesPost/>
    <ass-cons/>
    <bur-cons/>
    <coms-tech/>
    <secretariat/>
    <DailyUpdates />
    <TestimonialsCarouselOne className="about-page-testimonial" />
    <CallToActionTwo className="join-one__about" /> 
    <!-- //correction later new commit -->
    <ThreeBoxes /> 
    <VolunteerAbout />
    <!-- <SponsorsOne /> -->
    <Footer />
    <SearchPopup />
    <MobileDrawer />
  </div>
</template>

<script>
export default {
    
    head(){
      return {
        title: "CMA BENIN| Présentation"
      }
    }
  }

</script>
