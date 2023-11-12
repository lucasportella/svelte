<script>
  const componentMsg = 'Hello from component!'
  const isPromo = true;
</script>

<div class:promo={isPromo}>
  Here comes the component:
  {componentMsg}
</div>  

<style>
  div {
    color: red;
  }

  .promo {
    background-color: antiquewhite;
  }
</style>