<script>
export default {

  props:{
    project: Object, //passa il progetto come prop
  }
  
}
</script>

<template>
  <div class="project-card">

    <h2>{{ project.title}}</h2>
    <img src="" alt="">
    <p>{{project.description}}</p>

    
  </div>
</template>