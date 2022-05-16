

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

          <ul>
        <li>
          <span> <!-- daytime --> </span>
          <h3><!-- title --></h3>
          <span> <!-- description --> </span>
        </li>
      </ul>

          <ul>
        <li>
          <span> <!-- daytime --> </span>
          <h3><!-- title --></h3>
          <span> <!-- description --> </span>
        </li>
      </ul>


    <footer>
      <div> <!--not sure style: width="1080p" height="130px" -->
        <img src="./assets/STZH_SEB_Logo.png" width="230px" height="44px">
        <img src="./assets/Opportunity.png" width="296px" height="55px">
        <img src="./assets/SAG_Logo_De.png" width="273px" height="52px">
       </div> 
    </footer>

  </div>

</template>

<script>
export default {
  name: "App",
};
</script>

<style>


@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,400;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

#app {
  font-family: 'Roboto, sans-serif';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  background-color: #E5E5E5;
  text-align: left;
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
  position: absolute;
  padding-right: -4.46%;
  background: #0f05a0;

}
</style>
