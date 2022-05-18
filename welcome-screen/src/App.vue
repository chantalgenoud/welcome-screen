

<template>

<div id="app">

 <!-- <p>{{ getData() }}</p> -->
  <h1 class="site-title"> {{ title }} </h1>
  <span class="site-description">Heute ist der {{ currentDate }} </span>
  <p id="noEntries" v-if="!value">Keine Termine geplant!</p> <!--falls nichts in der db ist, kommt dieser Text -->
  <p> {{  title  }} </p>
  <p> {{  description  }} </p>
  <p> {{  event }}



 <!-- kein v-else yet--> 

  <!--
    <p> {{ entries.data.valueRanges[0].values }} </p>
  -->


 
  <div>   

   <!-- Dieser Code ist von Tugce -->  
  <!-- entry list -->

  <ul>

      <li v-for="event in entries" :key="event.id">
        <span> {{ event [8]}} </span>
      </li>
  </ul>
        <li
          v-for="entry in entries"
          :key="entry.id"
        >

          <span class="entry-daytime">{{  entry[1].replaceAll("/", ".")  }}</span>>br />
          <h3> class="entry-title">Ich bin ein Titel</h3>
          <span class="entry-description">Ich bin eine Beschreibung</span><br />
        </li>


  </div>

  <!--
          <span>{{entry}}</span><br />
          <h3>ich bin ein titel</h3>
          <span>ich bin eine beschreibung</span><br />
        </li>
      </ul>
  </div>  

  -->


      <ul class="entry-list"> </ul>

        
        <h1>Welcome to Opportunity</h1>


      <div class="blauesRechteck">
        <ul>
            <li>
            <span style=color:#EB5E00> 14.00 Uhr </span>
            <h3>Basisbeschäftigung Besuch</h3>
            <span>Interessierte für den zweiten Kurs werden uns besuchen</span>
          </li>
        </ul>
          </div>
[Vue warn]: Property or method "value" is not defined on the instance but referenced during render. Make sure that this property is reactive, either in the data option, or for class-based components, by initializing the property. See: https://vuejs.org/v2/guide/reactivity.html#Declaring-Reactive-Properties.

found in

---> <App> at src/App.vue
       <Root> vue.runtime.esm.js:619
[Vue warn]: Property or method "description" is not defined on the instance but referenced during render. Make sure that this property is reactive, either in the data option, or for class-based components, by initializing the property. See: https://vuejs.org/v2/guide/reactivity.html#Declaring-Reactive-Properties.

found in

---> <App> at src/App.vue
       <Root> vue.runtime.esm.js:619
[Vue warn]: Property or method "event" is not defined on the instance but referenced during render. Make sure that this property is reactive, either in the data option, or for class-based components, by initializing the property. See: https://vuejs.org/v2/guide/reactivity.html#Declaring-Reactive-Properties.

found in

---> <App> at src/App.vue
       <Root>
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

-->

 <!--footer-->
 
 <!--    <footer id="logos"> -->
   <footer class="footer">
            <img src="./assets/STZH_SEB_Logo.png" width="230px" height="44px">
            <img src="./assets/Opportunity.png" width="296px" height="55px">
            <img src="./assets/SAG_Logo_De.png" width="273px" height="52px">
    
      </footer>

</div>



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
      currentDate: "",
    };
  },

  
  computed: {
    gsheet_url() {
      return `https://sheets.googleapis.com/v4/spreadsheets/${this.sheet_id}/values:batchGet?ranges=A1%3AE100&valueRenderOption=FORMATTED_VALUE&key=${this.api_token}`;
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

};

</script>




 






<style>


@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,400;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');

#app {
  font-family: 'Roboto, sans-serif';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  background-color: #E8EFF4;
;
}


/** {
  background-color: #E5E5E5;
  text-align: left;
}
*/

h1 {
  text-align: left;
  font-family: 'Roboto', sans-serif;
  font-size: 62px;
  font-weight: 90;
}

.blauesRechteck {
  width: 960px;
  he</template>ight: 182px;
  background: #0f05a0;
  padding-left: 60px;
  padding-right: 60px;
}


.logos {
  position: fixed;
  text-align: center;
  width: 100%;
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

</style>
