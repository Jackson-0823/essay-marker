<template>
  <div>
    <main class="main">Main Content</main>
    <footer class="footer"></footer>
  </div>

    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>
                    <div class="icon-container">
                <ion-icon :icon="ioniconsLogoIonic" size="small" color="primary"></ion-icon>
                <h1 style="margin: 0 0 0 1em"> Your information<br>
                    <h6 >Good good study, day day up! </h6>
                </h1>
            


            </div>
                </ion-title>
            </ion-toolbar>
        </ion-header>

        <ion-content>
        <ion-list>
            <ion-item>
                <ion-avatar aria-hidden="true" slot="start">
                    <img alt="" src="@/img/albums-outline.svg" />
                </ion-avatar>
                <ion-label>My Profile</ion-label>
            </ion-item>
            <ion-item>
                <ion-avatar aria-hidden="true" slot="start">
                    <img alt="" src="@/img/recording-outline.svg" />
                </ion-avatar>
                <ion-label>Requirement History</ion-label>
            </ion-item>
            <ion-item>
                <ion-avatar aria-hidden="true" slot="start">
                <img alt="" src="@/img/analytics-outline.svg" />
                </ion-avatar>
                <ion-label>Data Analysis</ion-label>
            </ion-item>

        </ion-list>
      </ion-content>
        <ion-content class="ion-padding">
            <ion-button router-link="/">
                <ion-icon :icon="ioniconsLogOutOutline" />
                <ion-label>Logout</ion-label>
            </ion-button>

        </ion-content>
        <n-button @click="OnLogoutBtnClick" type="error" >Logout</n-button>
        <n-button quaternary @click="themeStore.toggleTheme">
                <template #icon>
                    <n-icon>
                        <Sunny v-if="themeStore.isDarkTheme" />
                        <Moon v-else />
                    </n-icon>
                </template>
                切换主题
            </n-button>
    </ion-page>
</template>

<script setup lang="ts">
import { useThemeStore } from '@/stores/theme';
import { Sunny, Moon } from '@vicons/ionicons5';

const themeStore = useThemeStore();
const router = useRouter();

function OnLogoutBtnClick() {
    router.push('/');
}

</script>

<style scoped>


.icon-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-top: 2em;
    margin-bottom: 1em;
}

.ion-padding{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-top: 50em;
    margin-bottom: 50em;
    margin-left: 200em;

}

.header {
  flex: 0 0 auto;
}

.main {
  flex: 1;
}

.footer {
  flex: 0 0 auto;
}
</style>