<template>

<div>
    <Header />
    <PageHeader pageTitle="Documents" pageName="Documents" />
    <br>
    <br>
    <doc-d-c></doc-d-c>
    <!-- <doc-d-cc></doc-d-cc> -->
    <doc-rma></doc-rma>
    <doc-dcpa></doc-dcpa>
    <rea></rea>
    <doc-nmab></doc-nmab>
    <Footer />
</div>

</template>

<script >

  export default {
    
    head(){
      return {
        title: "CMA BENIN| Documents"
      }
    }
  }
  </script>