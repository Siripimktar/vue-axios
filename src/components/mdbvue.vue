<template>
  <mdb-navbar color="indigo">
    <mdb-navbar-brand href="https://mdbootstrap.com/">
      <img src="https://mdbootstrap.com/img/logo/mdb-transparent.png" height="30" alt="">
    </mdb-navbar-brand>
  </mdb-navbar>
</template>


<script>
  import { mdbNavbar, mdbNavbarBrand } from 'mdbvue';
  export default {
    name: 'NavbarPage',
    components: {
      mdbNavbar,
      mdbNavbarBrand
    }
  }
</script>