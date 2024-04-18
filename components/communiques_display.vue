<template>
    <div class="container">
        <div class="row">
            <SectionTitle title="Communiqués" subTitle="CMA-BENIN" alignment="left" />
            <!--Four Icon Single-->
            <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">


                <!-- Audio Card -->


                <div class="pdf-accordion">
                    <div v-for="(item, index) in coms" :key="item.id" class="pdf-accordion-item">
                        <div class="pdf-accordion-title" @click="toggleAccordion(index)">
                            <h2 class="pdf-title">{{ item.title }}</h2>
                            <p class="pdf-author">{{ item.version }}</p>
                        </div>
                        <div class="pdf-accordion-content" :class="{ 'active': activeIndex == index }">
                            
                            <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
                                    
                                    <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
                                    <div class="pdf-card">
                                        <h2 class="pdf-title">
                                            Communiqué
                                        </h2>
                                        <a :href="item.video" target="_blank"
                                            class="pdf-download-button">Lire le communiqué</a>
                                    </div>
                                </div>
                            </div>
                            
                                <!-- <audio controls class="w-full">
                                    <source :src="item.audio" type="audio/mp3">
                                    
                                </audio> -->
                                <div v-for="(content, contentIndex) in item.comfiles" :key="contentIndex"
                                    class="content-item">
                                    <div class="max-w-md mx-auto bg-white p-4 rounded-lg shadow-md">
                                        <div class="pdf-card">
                                            <h2 class="pdf-title">
                                                {{ content.file_title }}
                                            </h2>
                                            <a :href="content.file_path" target="_blank"
                                                class="pdf-download-button">Lire le Communiqué</a>
                                        </div>
                                    </div>

                                </div>
                        </div>
                    </div>
                </div>



                <!-- Repeat this card for more audio listings -->

            </div>
        </div>
    </div>
</template>

<script>
import dataT from "~/data/data.json";
export default {
    props: {
        title: {
            type: String,
        },
        version: {
            type: String,
        },
        audio: {
            type: String,
        },
    },
    
        name: "communiques_display",

    data() {
        return {
            // news: [],
            coms: [],// Your data array
            activeIndex: -1
        };
    },

    methods: {
        async getDatas() {
            const apiLink = dataT.apiUrl.link;

            const res = await fetch(apiLink + "communique-library");
            const finalRes = await res.json();
            this.coms = finalRes.communiques;
        },
        toggleAccordion(index) {
            if (this.activeIndex == index) {
                this.activeIndex = -1; // Close if clicked again
            } else {
                this.activeIndex = index; // Open clicked accordion
            }
        }
    },
    mounted() {
        this.getDatas()
    },
};
</script>



<style scope>
.pdf-card {
    background-color: #f5f5f5;
    border: 1px solid #ccc;
    border-radius: 8px;
    padding: 20px;
    margin-bottom: 20px;
}

.pdf-title {
    font-size: 15px;
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
    padding: 8px 10px;
    font-size: 15px;
    border: none;
    border-radius: 999px;
    text-decoration: none;
    display: inline-block;
    transition: background-color 0.3s;
}

.pdf-download-button:hover {
    background-color: #0056b3;
}

.pdf-accordion-item {
    border-bottom: 1px solid #ccc;
}

.pdf-accordion-title {
    cursor: pointer;
    padding: 10px;
    background-color: #f5f5f5;
}

.pdf-accordion-content {
    display: none;
    padding: 10px;
}

.pdf-accordion-content.active {
    display: block;
}

.content-row {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.content-item {
    
    /* Adjust width as needed */
    margin-bottom: 10px;
}
</style>