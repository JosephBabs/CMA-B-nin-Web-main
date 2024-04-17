<template>
    <div class="committee-section" id="bureau-consulaire">
        <div class="committee-title section-title__title">Le Bureau consulaire</div>
        <div class="committee-text">
            <p>Il a pour mission de faciliter le développement d’actions et de partenariat visant la promotion du secteur de l’artisanat. Il est composé du Président et de quatre vice–présidents. (photo individuelle)</p>
            <ul>
                <li>La première VP chargée d’une part du registre des métiers. Elle peut également se voir confier des tâches spécifiques;</li>
                <li>La deuxième VP chargée de la formation professionnelle par apprentissage, de la reconnaissance des qualifications et des certifications professionnelles;</li>
                <li>Le troisième VP chargé du développement des entreprises et de l’évolution des métiers;</li>
                <li>Le quatrième VP chargé de la promotion du secteur de l’artisanat, de la communication et des relations avec les organisations professionnelles de l’artisanat.</li>
            </ul>
        </div>

        <div class="committee-grid">
            <div class="committee-member">
                <img src="~/assets/images/staff/bureau/sabine.jpg" alt="Sabine">
                <p style="font-weight: 800;" class="post">Sabine AKPLOGAN </p>
                <p >1ere Vice Présidente</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/bureau/lucie.jpg" alt="Lucie P. KATAGNA">
                <p style="font-weight: 800;"  class="post">Lucie P. KATAGNA </p>
                <p >2e Vice Présidente</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/bureau/elysee.jpg" alt="Élysée AHOUANTCHEDE">
                <p style="font-weight: 800;"  class="post">Élysée AHOUANTCHEDE  </p>
                <p >3e Vice Président</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/bureau/serge.jpg" alt="Serge BAH KPEVE">
                <p style="font-weight: 800;" class="post">Serge BAH KPEVE</p>
                <p >4e Vice Président</p>
            </div>
        </div>
        
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style lang="css" scoped>
.committee-section {
            background: #FFFEFE; /* Adjust the background color as needed */
            padding: 40px;
            text-align: center;
        }

        .committee-title {
            /* font-size: 24px;
            font-weight: bold;*/
            margin-bottom: 20px; 
        }

        .committee-text {
            margin-bottom: 20px;
            
            text-align: left;
            margin-bottom: 20px;
            background-color: #0171b0;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            padding:10px;
            color: #fff;
        }
        .post {
            background-color: #0171b0;
            padding:10px;
            text-align: center;
            color: #fff;
            width: 100%;
            bottom: 0;
        }

        .committee-grid {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 20px;
            justify-content: center;
        }
        @media (max-width: 768px) {
            .committee-grid {
                grid-template-columns: 1fr; /* Display in a single column */
            }
        }

        .committee-member { 
            /* Adjust the background color as needed */
            /* padding: 10px; */
            text-align: center;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .committee-member img {
            max-width: 100%;
            border-top-left-radius: 03%;
            border-top-right-radius: 03%;
            /* margin-bottom: 10px; */
        }

        .committee-member p {
            font-weight: bold;
        }
        .committee-member { 
            /* Adjust the background color as needed */
            /* padding: 10px; */
            text-align: center;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        .committee-member img {
            max-width: 100%;
            border-top-left-radius: 03%;
            border-top-right-radius: 03%;
            /* margin-bottom: 10px; */
        }

        .committee-member p {
            font-weight: bold;
        }


        

</style>