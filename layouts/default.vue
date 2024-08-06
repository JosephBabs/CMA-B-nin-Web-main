<template>
  <div class="page-wrapper" id="wrapper">
    <Nuxt />
  </div>
</template>


<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>


<script>

// import  "https://code.jquery.com/jquery-3.6.0.min.js";
export default {
  mounted() {


  

    this.$nextTick(() => {
      this.$nuxt.$loading.start();
      setTimeout(() => this.$nuxt.$loading.finish(), 500);
    });

    


  },
};
</script>
