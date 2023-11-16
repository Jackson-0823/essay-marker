<template>
     <ion-page>
        <ion-content class="ion-padding">
    
    
    <div class="big-box"></div>
    <!-- user bos 是白色的登陆框-->
    <div class="user-box">
        <div class="title">
            <div class="icon-container">

                <ion-icon :icon="ioniconsLogoIonic" size="large" color="primary"></ion-icon>
                <h1 style="margin: 0 0 0 1em">Essay Marker</h1>
            </div>

            <br/>
            <br/>
            <br/>

            <ion-list>
            <ion-item>
            <ion-input label-placement="floating" value="XXX@connect.hku.hk">
                <div slot="label">Email <ion-text color="danger">(Required)</ion-text></div>
            </ion-input>
            </ion-item>
            </ion-list>
            <br/>
            <ion-list>
            <ion-item>
            <ion-input label="Password input" type="password" value="password"></ion-input>
            </ion-item>
            </ion-list>

            <br/>
            <br/>
            <br/>
            <br/>
            
            <ion-button router-link="/tabs/list" expand="block" shape="round" class="welcome-button">
                    <ion-icon :icon="ioniconsLogInOutline" />
                    <ion-label>create an account</ion-label>

            </ion-button>            
        </div>
    </div>

    <ion-page>
        <ion-list :inset="true">
            <ion-item>
                <ion-icon :icon="ioniconsBookOutline" slot="start"></ion-icon>
                <ion-label>
                    <a target="_blank" rel="noopener noreferrer" href="https://www.youtube.com/watch?v=LpD9LjPSPyE">The instruction of how to create an account</a>
                </ion-label>
            </ion-item>
        </ion-list>
    </ion-page>
</ion-content>
    </ion-page>
</template>


<script setup lang="ts">
import { IonInput, IonItem, IonList } from '@ionic/vue';
import { defineComponent } from 'vue';



const ionHeaderWelcome = ref<HTMLElement | null>(null);
const welcomeBanner = ref<HTMLElement | null>(null);

onMounted(() => {
    // 计算剩余可用高度
    const calculateRemainingHeight = () => {
        if (welcomeBanner.value && ionHeaderWelcome.value) {
            const windowHeight = window.innerHeight;
            const headerHeight = ionHeaderWelcome.value.clientHeight;
            const remainingHeight = windowHeight - headerHeight;
            welcomeBanner.value.style.minHeight = `${remainingHeight}px`;
        }
    };

    setTimeout(() => {
        console.log('timeout');
        calculateRemainingHeight();
    }, 1);

    // 当窗口大小变化时重新计算高度
    window.addEventListener('resize', calculateRemainingHeight);
});
</script>


<style lang="scss" scoped>
.icon-container {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    margin-top: 5em;
    margin-bottom: 5em;
}

.big-box{
    position: fixed;
    top:0;
    left: 0;
    right: 0;
    bottom:0;
    background: url("http://img.tukppt.com/ad_preview/00/12/80/5dd62e71cf007.jpg!/fw/780")
    no-repeat;
    background-size:cover;
}

.user-box{
    border-radius:10px;
    width:300px;
    min-height:300px;
    background: white;
    margin: 80px auto;
    box-shadow: 5px #ccc;
}

.welcome-button {
    width: 20rem !important;
}
</style>