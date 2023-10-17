<script>
import axios from 'axios';
import ProjectCard from './components/ProjectCard.vue';

export default {
  components:{
    ProjectCard,
  },

  data(){
    return{
      projects: [], // la variabile che conterra i dati dei progetti
    };
  },
  methods: {
    fetchData(){
      axios.get('http://127.0.0.1:8000/api/projects')

      .then((response) => {
        this.projects = response.data.data;// salvo la lista dei progetti
        console.log(response);
      })

    }
    
  },

  mounted() {
    this.fetchData();//invosa la funzione fetchData
  },
  
}
</script>


<template>
  <main>
    <div class="container">
      <h1>benvenuto nel mio portfolio</h1>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nemo officiis quae temporibus placeat consectetur eius, ut debitis? Sequi quidem laborum inventore iure numquam nam, laboriosam assumenda qui nesciunt eum aut?</p>

      <ProjectCard v-for="project in projects" :key="project.id"></ProjectCard>



    </div>
  </main>

</template>