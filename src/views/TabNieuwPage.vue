<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Voeg een product toe</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Voeg een product toe</ion-title>
        </ion-toolbar>
      </ion-header>
      <ion-grid>
        <ion-row>
          <ion-col class="ion-text-center">Welk product wil je toevoegen?</ion-col> 
        </ion-row>

        <ion-row>
          <ion-col >
            <ion-item>
              <ion-input 
                label="Product"
                label-placement="stacked"
                placeholder="Naam product" 
                v-model="productNaam"
                required="true"
                @ion-blur="logProduct()"></ion-input>
            </ion-item>
            <ion-item>
              <ion-input 
                label="Prijs"
                label-placement="stacked"
                placeholder="10.00" 
                v-model="productPrijs"
                type="number"
                required="true"
                @ion-blur="logProduct()"></ion-input>
            </ion-item>
            <ion-item>
              <ion-select
                label="Categorie"
                label-placement="stacked" 
                interface="popover" 
                placeholder="Selecteer categorie"
                v-model="productCategorie"
                @ion-change="logProduct()">
                <ion-select-option value="0" disabled="true">Welk type product?</ion-select-option>
                <ion-select-option value="1">Fruit</ion-select-option>
                <ion-select-option value="2">Groente</ion-select-option>
              </ion-select>
            </ion-item>
          </ion-col>
        </ion-row>
        <ion-row>
          <ion-col>
            <ion-button expand="block" @click="verzendProduct()">Bevestig</ion-button>
          </ion-col>
        </ion-row>

        <!-- Het volgende deel staat hier enkel als DEMO voor de reactiviteit in Vue -->
        <!-- Het is niet nodig voor jouw project, maar je kan het gebruiken om de reactiviteit te testen -->
        <ion-row>
          <ion-col>
            <ion-item>
              <ion-label>Product: {{productNaam}}</ion-label>
            </ion-item>
            <ion-item>
              <ion-label>Prijs: {{productPrijs}}</ion-label>
            </ion-item>
            <ion-item>
              <ion-label>Categorienummer: {{productCategorie}}</ion-label>
            </ion-item>
          </ion-col>
        </ion-row>
      </ion-grid>
      
    </ion-content>
  </ion-page>
</template>

<script setup>
import { ref } from 'vue'
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonGrid, IonRow, IonCol, IonItem, IonLabel, IonInput, IonSelect, IonSelectOption, IonButton } from '@ionic/vue';

const productNaam = ref( '' );
const productPrijs = ref( 0.00 );
const productCategorie = ref( 0 );

const logProduct = () => {
  console.log(`naam: ${productNaam.value}, prijs: ${productPrijs.value}, categorie: ${productCategorie.value}`);
};

const verzendProduct = () => {
  // TODO: dit verder uitwerken en effectief het product verzenden
  logProduct();
};

</script>
