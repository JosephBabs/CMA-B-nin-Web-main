<template>
    <!--Four Icon Start-->
    <section class="four-icon" >
      <div class="container">
        <div class="row">
          <SectionTitle
              title="Métiers validés"
              subTitle="Documents CMA-BENIN"
              alignment="left"
              id="doc-mv"
            />
          <div
            class="col-xl-3 col-lg-6 col-md-6 wow fadeInUp"
            data-wow-delay="100ms"
          >
          
            <!--Four Icon Single-->
            
          </div>
          <div class="pdf-card">
              <h2 class="pdf-title">Métiers validés</h2>
              <p class="pdf-author">Par : Super Admin</p>
              <a href="https://app.cmabenin.bj/web/public/storage/docs/mv.pdf" class="pdf-download-button"
                >Télécharger PDF</a
              >
            </div>
        </div>
      </div>
    </section>
    <!--Four Icon End-->
  </template>
  
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
