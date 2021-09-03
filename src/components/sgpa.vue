<template>
  <div class="container">
    <!-- <i class="fab fa-medium"></i>
<i class="far fa-envelope"></i> -->
    <h1
      class="heading is-size-3 has-text-centered is-underlined has-text-weight-bold is-family-monospace"
    >
      SGPA-CGPA CALCULATOR
    </h1>
    <div class="box mt-6 tabs is-toggle is-toggle-rounded is-centered">
      <ul>
        <li @click="show=false" :class="{'is-active': !show}">
          <a>
            <span class="icon is-small"><i class="fas fa-graduation-cap"></i></span>
            <span>SGPA</span>
          </a>
        </li>
        <li @click="show=true" :class="{'is-active': show}" >
          <a>
            <span class="icon is-small"><i class="fas fa-graduation-cap"></i></span>
            <span>CGPA</span>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            show: false,
            
        }
    }
};
</script>

<style scoped></style>
