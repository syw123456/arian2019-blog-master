<template>
  <section class="container" :style="'background-color:' + bgColor + ''">

    <!--<div class="left-side">-->



        <ToggleButton
                @toggle="toggleButton()"
                :togglePosition="this.togglePosition"
                :toggleButtonColor="this.toggleButtonColor"
                :toggleButtonBoxShadow="this.toggleButtonBoxShadow"
        >
        </ToggleButton>


        <Navigation :linkColor="this.linkColor" :navBackgroundColor="this.navBackgroundColor"></Navigation>


      <nuxt />


      <div class="footer-links">
        <p style="color: #646464">connect with me</p>
        <a href="mailto:arianandcode@gmail.com">email</a>
        <a target="_blank" href="https://twitter.com/arian__prince">twitter</a>
        <a target="_blank" href="https://medium.com/@arian">medium</a>
        <a target="_blank" href="https://www.instagram.com/arian__prince">instagram</a>
      </div>





<!--
    <div class="right-side">

      <div class="colored-box" :style="'background-color:' + this.boxColor"></div>

    </div>-->

  </section>
</template>

<script>
import Navigation from '../components/Navigation.vue';
import ToggleButton from '../components/ToggleButton.vue';

export default {
  data() {
    return {
      page: 'index',
      darkMode: false,
      boxColor: '#98EFBD',
      togglePosition: 1,
//      toggleButtonColor: '#ACADAD',
      toggleButtonColor: '#98EFBD',
      toggleButtonBoxShadow: '1px 1px 1px #D3D3D3',
      bgColor: 'white',
      titleColor: 'black',
      currentPage: '',
      linkColor: '#707070',
      navBackgroundColor: 'white',
      media: [],
    }
  },


  computed: {

  },

  components: {
    Navigation, ToggleButton
  },

  methods: {



      toggleButton() {
          if(! this.darkMode) {
              this.activateDarkMode();
          } else {
              this.activateLightMode();
          }
      },

      activateDarkMode() {
          this.darkMode = true;
          this.darkModeProperties();
      },

      activateLightMode() {
          this.darkMode = false;
          this.lightModeProperties();
      },

      darkModeProperties() {
          this.togglePosition = 19;
          this.bgColor = 'black';
          this.titleColor = 'grey';
          this.boxColor = '#175A5A';
          this.linkColor = '#175A5A';
//          this.toggleButtonColor = '#ACADAD';
          this.toggleButtonColor = '#175A5A';
          this.navBackgroundColor = 'black';


          this.toggleButtonBoxShadow = 'initial'
      },

      lightModeProperties() {
          this.togglePosition = 1;
          this.bgColor = 'white';
          this.titleColor = 'black';
          this.boxColor = '#98EFBD';
          this.linkColor = '#707070';
//          this.toggleButtonColor = '#ACADAD';
          this.toggleButtonColor = '#ea7e7e';
          this.toggleButtonBoxShadow = '1px 1px 1px #D3D3D3';
          this.navBackgroundColor = 'white';
      },

      isItLate() {
          if(new Date().getHours() > 20) {
              return this.activateDarkMode();
          }
      }
  },

  created() {
      this.isItLate();

      let css = "text-shadow: 2px 2px rgb(0, 255, 99); font-size: 24px; font-family: sans-serif";

      console.log("%c\n\nMy senses tell me you must be some sort of super coder! 😎 \n\nI have open-sourced all of the code for this site, feel free to chat me:\n\n\nhttps://twitter.com/arian__prince\n\n\n", css);

  },


}


</script>

<style>

html {
  font-family: 'IBM Plex Sans', 'Helvetica Neue', 'Helvetica', 'Source Sans Pro', -apple-system, BlinkMacSystemFont, Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  text-align: left;
}
body{
  overflow: hidden;

}
*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}


.container {
  display: flex;
  /* justify-content: left; */
  align-items: center;
  /* text-align: left; */
  width: 100%;
  /* padding: 10px; */
  transition: all 350ms;
  /*height: 100vh;*/
}

.sidebar {
  /*width: 100px;*/
  margin-left: 40px;
  display: flex;
  /* align-items: center; */
  /* justify-content: center; */
  /*height: calc(100vh - 20px);*/
  /* padding-top: 10%; */
  padding-bottom: 34px;
}

.padded-bottom {
  padding-bottom: 20px;
}

.col-2 {
  width: 50%;
  flex-flow: column;
  display: flex;
  /*align-items: flex-end;*/
}


.left-side {
  height: 100vh;
  position: relative;
  width: 70%;
  flex-flow: column;
  display: flex;
  /*align-items: flex-end;*/
}

.right-side {
  height: 100vh;
  width: 30%;
  flex-flow: column;
  display: flex;
  transition: all 500ms;
  /*align-items: flex-end;*/
}

.padded-left {
  padding-left: 100px;
}

.content {
  max-width: 700px;
  display: flex;
  flex: 1;
  padding-left: 100px;
  padding-right: 100px;
  flex-flow: column;
  justify-content: center;
  height: 100vh;
}


a {
  transition: all 350ms;
}

a:hover {
  transition: all 350ms;
  color: #5099d7;
   background: -webkit-linear-gradient(#65ff78, #5099d7);
   -webkit-background-clip: text;
   -webkit-text-fill-color: transparent;
}


.footer-links {
  display: flex;
  flex-flow: row;
  width: 100%;
  height: 40px;
  align-items: center;
  margin-left: 100px;
  position: absolute;
  bottom: 0;
  /*max-width: 500px;*/
}

.footer-links a {
  margin-right: 20px;
}

.footer-links p {
  margin-right: 20px;
}

.big {
  font-size: 1.5em;
  /*color: #4B4B4B;*/
}

a {
  text-decoration: none;
  text-align: left;
  color: rgb(86, 107, 140);
  cursor: pointer;
}

.name {
  /*margin-top: 100px;*/
  /*text-orientation: sideways;*/
  /*writing-mode: vertical-rl;*/
  /*transform: rotate(-180deg);*/
  font-size: 3em;
}

h1 {
  /*opacity: 0;*/
  font-size: 3em;
  font-weight: 500;
  color: #3B3B3B;
  /*animation: fadeIn 0.5s linear 0.2s forwards;*/
}

h2 {
  /*opacity: 0;*/
  font-size: 2.5em;
  font-weight: 500;
  color: #646464;
  /*animation: fadeIn 0.4s linear 0.7s forwards;*/
}



.nuxt-link-exact-active {
  color: #5099d7;
  background: -webkit-linear-gradient(#65ff78, #5099d7);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.tagline {
  /*margin-bottom: 20px;*/
}

.button {
  margin-top: 10px;
  /*margin-bottom: 100px;*/
  /*opacity: 0;*/
  animation: colorfulFadeIn 3s linear 1.3s forwards;
  color: #606060;
  border: 1px solid #2e2e2e;
  padding: 6px 12px;
  /* margin-top: 50px; */
  border-radius: 6px;
  transition: all 400ms;
  box-shadow: 1px 1px 1px #2e2e2e;
  text-align: center;
  width: 110px;
  width: fit-content;
}

.learn-more:hover {
  box-shadow: 1px 1px 1px  rgb(23, 90, 90);
  border: 1px solid rgb(23, 90, 90);
  color: rgb(23, 90, 90);
}

.colored-box {
  width: 100%;
  height: 100vh;
  /*height: -webkit-fill-available;*/
  transition: all 350ms;
  position: fixed;
}


.fade-in {
  animation: fadeIn 0.4s ease-in-out forwards;
}

@keyframes fadeIn {
  0% {
    opacity: 0;

  }
  100% {
    opacity: 1;

  }
}


@keyframes colorfulFadeIn {
  0% {
  }
  25% {
    border-color: #2d4f68;
  }
  50% {
    border-color: #2d4f68;
  }
  75% {
    border-color: #4b5e6c;
  }
  100% {
  }
}

/*TRANSITIONS START*/
.page-enter-active {
  animation: acrossIn 0.6s ease-out both;
}

.page-leave-active {
  animation: acrossOut 0.6s ease-in both;
}

@keyframes acrossIn {
  0% {
    opacity: 0;
    /*transform: translate3d(100%, 0, 0);*/
  }
  100% {
    opacity: 1;
    /*transform: translate3d(0, 0, 0);*/
  }
}

@keyframes acrossOut {
  0% {
    opacity: 1;
    /*transform: translate3d(0, 0, 0);*/
  }
  100% {
    opacity: 0;
    /*transform: translate3d(-100%, 0, 0);*/
  }
}
/*TRANSITIONS END*/

@media only screen and (max-width: 999px) {

  .left-side {
    width: calc(100% - 200px);
    flex-flow: column;
    display: flex;
    /*align-items: flex-end;*/
  }

  .right-side {
    width: 200px;
    flex-flow: column;
    display: flex;
    /*align-items: flex-end;*/
  }
}


@media only screen and (max-width: 799px) {

  .left-side {
    width: calc(100% - 80px);
    flex-flow: column;
    display: flex;
    /*align-items: flex-end;*/
  }

  .right-side {
    width: 80px;
    flex-flow: column;
    display: flex;
    /*align-items: flex-end;*/
  }

  .padded-left {
    padding-left: 50px;
  }

  .footer-links p {
    display: none;
  }

}



@media only screen and (max-width: 599px) {

  .name {
    font-size: 2.5em;
  }

  .tagline {
    font-size: 2em;
  }

  .container {
    flex-wrap: wrap;
  }

  .left-side {
    width: 100%;
    flex-flow: column;
    display: flex;
    height: 100vh;
    /*align-items: flex-end;*/
  }

  .right-side {
    /*width: 100%;*/
    /*flex-flow: column;*/
    display: none;
    /*height: 40px;*/
    /*align-items: flex-end;*/
  }

  .padded-left {
    padding-left: 0;
  }


  .text-container {
    /*max-height: initial;*/
    /*margin-top: 52px;*/
    max-width: initial;
    margin-top: 20px;
  }





  .content {
    width: initial;
    padding-right: 20px;
    padding-left: 20px;
    position: relative;
    z-index: 1;
  }

  .footer-links {

    padding-left: 20px;
    padding-right: 10px;
    margin-left: initial;
    /*justify-content: space-around;*/
    /*border-top: 1px solid grey;*/
    box-shadow: -1px -1px 5px 0px rgba(128, 128, 128, 0.2);
    position: fixed;
    bottom: 0;
    z-index: 2;
  }

  .footer-links a {
    /*margin-right: inial;*/
  }

}

</style>
