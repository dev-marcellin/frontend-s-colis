<template>
  <div class="container-fluid h-100">
    <div class="row h-100 ">
      <bordlateral  creer="Enregistrer un colis" data="envoi" admin="Gérant de branche" branche1="reception" r1="/branche/enregistrer" r2="/branche/envoi"></bordlateral>
      <main class="col">
        <navbar></navbar>
        <div class="bord">
          <h2 class="text-center">Historique des colis</h2>
        </div>

        <div class="row row-cols-1 row-cols-md-3 g-4">
          <br />
         
        <p class="text-center">Total: </p>
          <table class="table table-success table-striped">
  <thead>
    <tr>
      <th scope="col">N°</th>
      <th scope="col">Code</th>
      <th scope="col">Description</th>
      <th scope="col">Prix</th>
      <th scope="col">Depart</th>
        <th scope="col">Destination</th>
    </tr>
  </thead>
  <tbody>
    <tr scope="row" v-for="(element,index) in tableau" :key="element"> 
      <!-- scope="row" v-for="element in tableau" :key="element.code">{{element.code}} -->
       <th > {{index}}</th>
      <td> {{element.code}}</td>
      <th>{{element.description}}</th>
      <th>{{element.prix}}</th>
      <th>{{element.depart}}</th>
      <th>{{element.destination}}</th>

    </tr>
   
  </tbody>
</table>
         
            

        </div>
      </main>
    </div>
  </div>
</template>

<script>
import bordlateral from "./bordlateral.vue";
import navbar from "./navbar.vue";



export default {
  name: "app",
  components: { bordlateral, navbar },
  data() {
    return {
      tableau,
      total
      

    };
  },
  methods: {
    enregistrer(){
 
    }
  },
  created(){
  let tempo = 0;
    axios.get("http://localhost:5000/api/infos/branche/historique/611bc8be609fe50e2eedbae3")
    .then(response => { 
      
      this.tableau = response.data;

      console.log(this.tableau);
  
    })
    /*for(let i=0; i<this.tableau.length; i++){
        tempo+=this.tableau[i].prix ;

      }
      this.total= tempo ;
      
        console.log(this.total);*/

  }
  
  
};
</script>