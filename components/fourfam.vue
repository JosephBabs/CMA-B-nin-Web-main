<template>
    <!--Team One Start-->
    <section class="team-one">
      <div class="container">
        <SectionTitle
          title=" Huit branches des métiers de l'artisanat ?"
          subTitle="Quelles sont les"
        />
        <div class="row">
          <div
            class="col-xl-4 col-lg-4"
            v-for="item in fourFam"
            :key="item.index"
          >
            <VolunteerCard
              :thumbnail="item.thumbnail"
              :title="item.title"
              :designation="item.designation"
              :excerpt="item.excerpt"
              :social="item.social"
            />
          </div>
          <!-- /.col-xl-4 col-lg-4 -->
        </div>
      </div>
    </section>
    <!--Team One End-->
  </template>
  
  <script>
  import SectionTitle from "~/components/SectionTitle";
  import VolunteerCard from "~/components/VolunteerCard";
  import data from "~/data/data.json";
  export default {
    components: {
      SectionTitle,
      VolunteerCard,
    },
    data() {
      return {
        fourFam: data.fourFam.slice(0, 8),
      };
    },
  };
  </script>
  