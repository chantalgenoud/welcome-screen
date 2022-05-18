

<template>

<div id="app">

 <!-- <p>{{ getData() }}</p> -->
  <h1 class="site-title"> {{ title }} </h1>
  <span class="site-description">Heute ist der {{ currentDate }} </span>



        <ul class=padding>
            <div v-if="entries">
              <li v-for="event in entries" :key="event.id" class="unlist blauesRechteck">
                   <!-- hier sollte ein Loop kommen, was ich aber verpasst habe und event oder entry? ist mir nicht ganz klar -->
              <span class=uhrzeit style=color:#EB5E00> {{  event[0]  }}  Uhr  {{  event[1].replaceAll("/", ".")  }} </span>
              <h3 class=beschreibung style=color:#ffc21a> {{  event[2]  }}</h3>
              <span style=color:#ffc21a> {{ event [3]  }}  </span>
              </li>
            </div>
            <h3 v-else>Keine Termine geplant!</h3>
        </ul>
  

<footer>
  <div class="footer">
          <img src="./assets/STZH_SEB_Logo.png" width="230px" height="44px">
          <img src="./assets/Opportunity.png" width="296px" height="55px">
          <img src="./assets/SAG_Logo_De.png" width="273px" height="52px">
  </div>
</footer>

</div>

</template>

<script>
import axios from "axios"; // axios ist einen db für http anfragen im backend

export default {
  name: "App",
  data() {
    return {
      title: "Welcome to Opportunity",
      sheet_id: "1a81aI0Y8ViZO0tI92h2YSMqVQJ8hmNNMyMylXgvwiU4",
      api_token: "AIzaSyA-qeDXOhEeQDA0vQf7LgkF7DQtGnAtmAU",
      entries: [],
      currentDate: "18.06.2022",
    };
  },

  
  computed: {
    gsheet_url() {
      return `https://sheets.googleapis.com/v4/spreadsheets/${this.sheet_id}/values:batchGet?ranges=A2%3AE100&valueRenderOption=FORMATTED_VALUE&key=${this.api_token}`;
    },
  },

  methods: {
    getData() {
      axios.get(this.gsheet_url).then((response) => {
        this.entries = response.data.valueRanges[0].values;
      });
    },
},


  mounted() {
    this.getData();
  },
/* Hier kommt das mit dem Intervall */

};

</script>



<style>


@import url('https://fonts.googleapis.com/css2?family=Inter:wght@500;900&display=swap');

@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,400;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

#app {
  font-family: 'Inter', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  background-color: #E8EFF4;
;
}


h1 {
  text-align: left;
  font-family: '', sans-serif;
  font-size: 62px;
  font-weight: 90;
}

.blauesRechteck {
  padding: 40px;
  width: 840px;
  height: 102px;
  background: #0f05a0;
  margin-left: 60px;
  margin-right: 60px;
  margin-bottom: 40px;
}


/* Dieser Code ist von Tugce */
.footer {
  display: flex;
  justify-content: space-between;
  box-sizing: border-box;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  padding: 40px;
  background: #fff;
}

.footer img {
  height: 50px;
}

.unlist {
  list-style-type: none;
}

.padding {
  padding: 30px;
}

.uhrzeit {
  font-family: 'Inter', sans-serif;
  font-weight: 900;
  font-size: 28px;
  color: #EB5E00;
}

.beschreibung {
  font-family: 'Inter', sans-serif;
  font-weight: 500;
  font-size: 28px;
  color: #d1ab87;
}



</style>
