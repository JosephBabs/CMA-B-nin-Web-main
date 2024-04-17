<template>
    <div id="assemblee-consulaire">
    <!-- <div class="divider"></div> -->
        <div class="assemblee-consulaire-section">
        
        <div class="text-content">
            
            <h2  class="section-title__title" style="color:rgb(53, 53, 53);">Assemblée consulaire</h2>
            <p class="boxed">
                C'est l’organe d’administration de la CMA-Bénin. Elle est investie des pouvoirs les plus étendus pour prendre toutes les décisions nécessaires ou concourant au bon fonctionnement et à l’accomplissement des missions de la Chambre. Elle est composée de 80 élus répartis en 08 branches conformément à la nomenclature des métiers de l’artisanat. 
            </p>
            <img src="~/assets/images/backgrounds/photoAG1.jpg" width="100%" height="auto" alt="Photo de famille" >
        </div>
    </div>
            
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
.divider {
            width: 100%;
            height: 2px;
            background-color: #050505; /* Adjust the color as needed */
        }
        .assemblee-consulaire-section {
            /* position: relative; */
            /* height: 100vh; */
            /* background: url('~/assets/images/backgrounds/photoAG.jpg') center/cover no-repeat; */
            color: #111111;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            margin-bottom: 3em;
        }

        .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            /* background: rgba(0, 0, 0, 0.808); */
        }

        .text-content {
            z-index: 1; 
            padding: 100px;
            text-align: center;
            margin-bottom: 20px;
            background-color: #FFFFFF;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            padding:10px;
            color: #383838;
        }
        .text-content img {
            max-width: 100%;
            margin-top: 20px; /* Adjust the margin as needed */
            
        }
       
</style>