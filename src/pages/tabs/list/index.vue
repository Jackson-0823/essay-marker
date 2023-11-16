<template>
    <ion-page>
      <ion-header>
        <ul>
            <li>
            <ion-toolbar>
            <ion-title>Search your name</ion-title>
            </ion-toolbar> 
            </li>
            <li>
            <ion-searchbar show-clear-button="always" :clear-icon="trashBin" value="Custom name"></ion-searchbar>
            </li>
        </ul>

      </ion-header>
      <ion-content>
        <ion-list>
            <ion-item>
                <ion-avatar aria-hidden="true" slot="start">
                    <img alt="" src="https://ionicframework.com/docs/img/demos/avatar.svg" />
                </ion-avatar>
                <ion-label>Huey</ion-label>
            </ion-item>
            <ion-item>
                <ion-avatar aria-hidden="true" slot="start">
                    <img alt="" src="https://ionicframework.com/docs/img/demos/avatar.svg" />
                </ion-avatar>
                <ion-label>Dewey</ion-label>
            </ion-item>
            <ion-item>
                <ion-avatar aria-hidden="true" slot="start">
                    <img alt="" src="https://ionicframework.com/docs/img/demos/avatar.svg" />
                </ion-avatar>
                <ion-label>Louie</ion-label>
            </ion-item>
            <ion-item>
                <ion-avatar aria-hidden="true" slot="start">
                    <img alt="" src="https://ionicframework.com/docs/img/demos/avatar.svg" />
                </ion-avatar>
                <ion-label>Fooie</ion-label>
            </ion-item>
        </ion-list>
      </ion-content>
    </ion-page>
  </template>

<script lang="ts">
  import { IonSearchbar } from '@ionic/vue';
  import { defineComponent } from 'vue';
  import { trashBin } from 'ionicons/icons';

</script>