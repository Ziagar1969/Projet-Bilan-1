<template>
  <div>
    <h3>Vous trouverez ici mes premières réalisations de développeur Web</h3>
    <div class="projets">
      <article class="cvonline" @click="openModal('contenu1')">
        <h5>CV online</h5>
        <img src="../assets/img/cvonline.png" alt="CV online">
      </article>
      <article class="cahierdc" @click="openModal('contenu2')">
        <h5>Cahier des Charges</h5>
        <img src="../assets/img/cdc.png" alt="Cahier des Charges">
      </article>
      <article class="espcom" @click="openModal('contenu3')">
        <h5>Espace de commentaires</h5>
        <img src="../assets/img/commentaires2.png" alt="Espace de commentaires">
      </article>

      <!-- 4ème projet: Météo -->
      <article class="meteo" @click="openModal('contenu4')">
        <h5>Météo</h5>
        <!-- miniature : soit une image, soit le widget réduit -->
        <MeteoWidget class="mini-meteo" />
      </article>
    </div>

    <!-- Modales inchangées -->
    <Modale2 ref="contenu1">
      <h2>{{ modalTitle }}</h2>
      <p>{{ modalTexte }}</p>
      <a href="https://github.com/Ziagar1969/cvonline" target="_blank">
        Télécharger le projet
      </a>
    </Modale2>
    <Modale2 ref="contenu2">
      <h2>{{ modalTitle }}</h2>
      <p>{{ modalTexte }}</p>
      <a href="../assets/downloads/corrigecahierdcharges.pdf">
        Télécharger le projet
      </a>
    </Modale2>
    <Modale2 ref="contenu3">
      <h2>{{ modalTitle }}</h2>
      <p>{{ modalTexte }}</p>
      <a href="https://github.com/Ziagar1969/PGComments" target="_blank">
        Télécharger le projet
      </a>
    </Modale2>

    <!-- Nouvelle modale pour la météo -->
    <Modale2 ref="contenu4">
      <h2>{{ modalTitle }}</h2>
      <p class="modal-texte">{{ modalTexte }}</p>
      <MeteoWidget />
      <img :src="formUdemy" alt="Form Udemy" class="modal-image" />
    </Modale2>
  </div>
</template>

<script>
import Modale2 from "../components/Modale2.vue"
import MeteoWidget from "../components/MeteoWidget.vue"
import formUdemy from "../assets/img/formUdemy.jpg"
export default {
  name: "Realisations",

    components: {
        Modale2,
        MeteoWidget
    },

    data() {
    return { modalTitle: "", modalTexte: "", formUdemy }
  },
    methods: {
        openModal(ModalId) {
            switch (ModalId) {
                case "contenu1":
                    this.modalTitle = "CV online";
                    this.modalTexte = "CV conçu en HTML et CSS, selon les normes W3C";
                    break;
                case "contenu2":
                    this.modalTitle = "Cahier des Charges";
                    this.modalTexte = "Document incontournable pour bien échafauder un article en tenant comte des besoins du client, de ses objectifs et de ceux de l'entreprise,des contraintes techniques, des fonctionnalités que l'on désire implémenter";
                    break;
                case "contenu3":
                    this.modalTitle = "Espace de commentaires en ligne";
                    this.modalTexte = "Création d'une page de commentaires en ligne, permettant d'ajouter un commentaire à la liste de commentaires existants. Les champs d'input se vident après l'ajout du commentaire.";
                    break;
                case "contenu4":
                    this.modalTitle = "Widget Météo";
                    this.modalTexte = `J'ai réalisé ce travail au cours d'une formation Udemy.
                    Il s'agit d'un widget météo qui affiche les conditions météorologiques actuelles pour une ville donnée en utilisant une API météo.`;
                    break;
            }
            this.$refs[ModalId].openModal();
        },
    },
};
</script>

<style scoped>
.projets {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-template-areas:
      "cvonline cahierdc"
      "espcom meteo";
    gap: 2em;
    margin-bottom: 2em;
}
article {
    display: flex;
    box-shadow: 0 2px 8px rgba(0,0,0,0.07);
    flex-direction: column;
    flex-wrap: wrap;
    height: auto;
    padding: 1.5em 1em;
    transition: box-shadow 0.2s, transform 0.2s;
    cursor: pointer;
}
article:hover {
   box-shadow: 0 4px 16px 2px rgb(0 0 3 / 0.12);
}
article img {
    width: 100%;
    margin-bottom: 1em;
    border-radius: 8px;
    object-fit: cover;
}
.cvonline {
    grid-area: cvonline;
    display: flex;
    flex-direction: column;
}
.cahierdc {
    grid-area: cahierdc;
    display: flex;
    flex-direction: column;
}
.espcom {
    grid-area: espcom;
    display: flex;
    flex-direction: column;
}
.meteo {
    grid-area: meteo;
    display: flex;
    flex-direction: column;
}
/* mini version du widget */
.mini-meteo {
  min-height: 120px;
  overflow: hidden;
  border-radius: 8px;
}
h3 {
    color: greenyellow;
    font-style: italic;
    width: fit-content;
    padding-bottom: 10px;
}
h5 {
    color: rgb(102, 102, 204);
    background-color: rgb(158, 192, 98);
    padding: 1%;
    border-radius: 1%;
}
.modal-image {
  max-width: 40%;
  height: auto;
  border-radius: 6px;
  margin-left: 60%;
  padding-top: 1rem;
  padding-right: 1rem;
}

.modal-texte {
  line-height: 1.6;        
  text-align: left;     /* alignement */
  white-space: pre-wrap;   /* conserve les sauts de ligne \n */
  hyphens: auto;           /* césure automatique */
  margin-top: 1rem;
  padding-left: 0.5rem;
  padding-right: 0.5rem;

}

/* sur petits écrans, repasse à une colonne */
@media (max-width: 800px) {
  .modal-texte {
    column-count: 1;
  }
}

@media screen and (max-width:800px) {
    .projets {
        grid-template-columns: 1fr;
        grid-template-areas:
          "cvonline"
          "cahierdc"
          "espcom"
          "meteo";
    }
}
</style>
