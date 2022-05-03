<template>
 <nav class="navbar navbar-expand-lg fixed-tp  p-2">
        
    <div class="container-fluid"> 
    <router-link to="/" class="navbar-brand p-3"><span class="oat">oat</span><span>hub</span></router-link>
   <!-- <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="fa fa-bars"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav ms-auto  p-3 mb-lg-0">
        <li class="nav-item">
          <router-link :to="{'name':'home'}" class="nav-link">Bootcamp</router-link>
        </li>
        <li class="nav-item">
          <router-link :to="{'name':'home'}" class="nav-link">Instructors</router-link>
        </li>
        
       
      </ul>
    </div>


    -->
        </div>
    </nav>
</template>


<script>
export default {
  name:'Navbar'
}
</script>
<style scoped>

.navbar .nav-link, .navbar-brand{
    color:#16283d;
}

.nav-link{
    font-size: 1.2rem;
}

.navbar-brand{
    font-size: 2.5rem;
    font-family: 'Michroma', sans-serif;
}

.oat{
    font-size:2.5rem;
    font-weight: 1000;
}

</style>