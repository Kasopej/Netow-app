<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-brand">
      <router-link to="/" class="navbar-brand bg-white mr-lg-5" href="#"><img src="assets/img/netow_logo_small.png" alt="Netow Logo"></router-link>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse ml-lg-4 ml-xl-5 d-lg-flex justify-content-between"
        id="navbarSupportedContent">
        <ul class="navbar-nav">
          <li class="nav-item active pr-3">

            <router-link to="/" class="nav-link">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/about" class="nav-link">About</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/services" class="nav-link">Our Serices</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/blog" class="nav-link">Blog</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/careers" class="nav-link">Careers</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/contact" class="nav-link">Contact Us</router-link>
          </li>

        </ul>
        <form class="form-inline my-2 my-lg-0 search-form d-inline-block">
          <input class="form-control bg-none py-1" type="search" aria-label="Search">
          <button class="btn pt-2 pt-md-0 bg-none search-button" type="submit"><i
              class="fa fa-search"></i></button>
        </form>
      </div>
    </nav>
</template>

<script>
export default {
    name: 'Header',
    /*
    computed: {
      active(){
        let menuLinks = Array.from(document.getElementsByClassName('nav-link'));
        let isActive = '';
        menuLinks.forEach(element => {
          if(element.textContent === this.$router.currentRoute.name){
            isActive = true ;
          }
        });
        return {active: isActive,};
      }
    },
    */
}
function findActive(){
  let links = Array.from(document.getElementsByClassName('nav-link'));
  links.forEach((el) => {
    if(el.classList.contains('router-link-exact-active')) {
      el.innerHTML = '<s>' + el.innerHTML + '</s>';
    }
    else {el.innerHTML = '<a>'+ el.textContent + '</a>'}
  })
  
}
window.onload =findActive;
document.body.onclick = findActive;

</script>

<style>

</style>