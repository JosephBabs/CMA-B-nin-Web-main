<template>
    <div class="committee-section" id="s-general">
        <div class="committee-title section-title__title">Le secrétariat Général</div>
        
        <div class="committee-grid">
            <div class="committee-member">
                <img src="~/assets/images/staff/joel.jpg" alt="Joel">
                <p style="font-weight: 800;" class="post">Joel BOUILLAUD</p>
                <p >Secretaire général</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/cyr.jpg" alt="Cyr">
                <p style="font-weight: 800;"  class="post">Cyr DAVODOUN </p>
                <p >Secretaire général adjoint</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/eric.jpg" alt="Eric">
                <p style="font-weight: 800;"  class="post">Eric OKE </p>
                <p >Directeur de l'administration et des finances</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/joseph.jpg" alt="Joseph">
                <p style="font-weight: 800;" class="post">Joseph ZINVOEDO </p>
                <p >Personne Responsable des Marchés Publics</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/celestin.jpg" alt="Celestin">
                <p style="font-weight: 800;"  class="post">Célestin DAKO </p>
                <p >Responsable formation</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/lucrece.jpg" alt="Lucrece">
                <p style="font-weight: 800;"  class="post">Lucrèce DEBADE </p>
                <p >Cheffe Cellule communication et archivage</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/rufin.jpg" alt="Rufin">
                <p style="font-weight: 800;" class="post">Rufin TOSSOU </p>
                <p >Chef service administratif et financier</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/nadine.jpg" alt="Nadine">
                <p style="font-weight: 800;" class="post">Nadine KOHOUFO </p>
                <p >Secretaire particulière</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/vivienne.jpg" alt="Vivienne">
                <p style="font-weight: 800;" class="post">Vivienne CODJIA </p>
                <p >Assistante du Secrétaire général</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/come.jpg" alt="Come">
                <p style="font-weight: 800;"  class="post">Come TOUNSE </p>
                <p>Assistant de la personne responsable des marchés publics</p>
            </div>
            <div class="committee-member">
                <img src="~/assets/images/staff/cendra.jpg" alt="Cendra">
                <p style="font-weight: 800;" class="post"> Cendra DOSSOU-YOVO </p>
                <p >Sécrétaire Administrative</p>
            </div>
            <div class="committee-text">
            <p>La CMA-Bénin dispose de services techniques et administratifs placés sous l’autorité d’un Secrétaire Général.
                Le Secrétariat Général assure de manière permanente la gestion opérationnelle des activités de la chambre. Il est responsable de l’exécution du budget. 
                </p>
            
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
            background: #f0f0f0; /* Adjust the background color as needed */
            padding: 40px;
            text-align: center;
        }

        .committee-title {
            /* font-size: 24px;
            font-weight: bold; */
            margin-bottom: 20px;
        }

        .committee-text {
            margin-bottom: 20px;
            background-color: #0171b0;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
            padding:10px;
            text-align: justify;
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
</style>