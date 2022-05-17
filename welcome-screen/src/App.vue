

<template>
    <div id="app">
    

      
      <h1>Welcome to Opportunity</h1>
    <!--<span> </span> -->

    <div class="blauesRechteck">
      <ul>
          <li>
          <span style=color:#EB5E00> 14.00 Uhr </span>
          <h3>Basisbeschäftigung Besuch</h3>
          <span>Interessierte für den zweiten Kurs werden uns besuchen</span>
        </li>
      </ul>
        </div>

    <div class="blauesRechteck"> 
      <ul>
        <li>
          <span> <!-- daytime --> </span>
          <h3>LOREM IPSUM DOLOR></h3>
          <span> <!-- description --> </span>
        </li>
      </ul>
    </div>

         
    <div class="blauesRechteck"> 
          <ul>
        <li>
          <span> <!-- daytime --> </span>
          <h3>LOREM IPSUM DOLOR</h3>
          <span> <!-- description --> </span>
        </li>
      </ul>
    </div>




    <footer id="logos">
          <img src="./assets/STZH_SEB_Logo.png" width="230px" height="44px">
          <img src="./assets/Opportunity.png" width="296px" height="55px">
          <img src="./assets/SAG_Logo_De.png" width="273px" height="52px">
  
    </footer>

</div>

</template>

<script>
export default {
  name: "App",
};
</script>

<!--
import axios from "axios";

DATA =
sheet_id: "",
api_token: "AIzaSyA-qeDXOhEeQDA0vQf7LgkF7DQtGnAtmAU", 


COMPUTED =
function ()  {
  return () {
    return ´https://sheets.googleapis.com/v4/spreadsheets/${**sheet id**}/values:batchGet?ranges=A1%3AE100&valueRenderOption=FORMATTED_VALUE&key=${**token**}`;

  },
}
-->
<style>


@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,400;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

#app {
  font-family: 'Roboto, sans-serif';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}





h1 {
  text-align: left;
  font-family: 'Roboto', sans-serif;
  font-size: 62px;
  font-weight: 90;
}

.blauesRechteck {
  width: 960px;
  height: 182px;
  background: #0f05a0;
}


.logos {
  position: fixed;
  text-align: center;
  width: 100%;

}

</style>
