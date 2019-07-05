<template>
  <div class="about">
    <div class="container-about">
          <h1>About My Candies</h1>
      <div class="row">
        <div class="col-8">
          <p> {{ sugarText1 }} </p>
        </div>
        <div class="col-4">
          <img src="../assets/animals-assorted-blur.jpg" />
        </div>
        <div class="col-4">
          <img src="../assets/animals-assorted-background.jpg" />
        </div>
        <div class="col-8">
          <p> {{ sugarText2 }} </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
   // returning text in required area
      sugarText1: "Candy lemon drops pastry chupa chups sesame snaps donut. Sweet pudding jelly-o cheesecake liquorice liquorice. Fruitcake gummi bears sugar plum. Cotton candy macaroon ice cream. Carrot cake bonbon apple pie sweet roll jujubes topping cotton candy cheesecake. Chocolate bar macaroon dragée cheesecake caramels cookie bear claw halvah tootsie roll. Candy canes oat cake icing soufflé cake chupa chups tiramisu. Cupcake pudding soufflé. Icing brownie powder sesame snaps chupa chups fruitcake icing oat cake apple pie. Candy canes muffin jelly-o toffee candy canes candy canes chocolate cake wafer brownie. Icing liquorice wafer cupcake caramels cupcake. Oat cake brownie cake. Jelly beans apple pie tiramisu ice cream jelly beans biscuit tart candy brownie. Jujubes gummies fruitcake dragée tiramisu tiramisu fruitcake chupa chups jelly beans.",
      sugarText2: "Cookie muffin marshmallow jelly beans gummi bears pastry cupcake icing. Pie tiramisu jujubes cookie icing muffin jelly-o. Pie liquorice tootsie roll cake. Cotton candy gummi bears cake biscuit. Gummies bear claw macaroon cookie jelly. Gingerbread bonbon bonbon. Cheesecake jelly-o toffee liquorice biscuit. Sesame snaps sweet ice cream soufflé caramels bear claw apple pie liquorice. Sugar plum biscuit sweet. Pie gingerbread pie powder tiramisu tart candy canes pastry croissant. Topping apple pie sweet roll lemon drops macaroon halvah sugar plum sweet. Dessert chocolate cake pie. Candy canes caramels caramels. Chupa chups pudding cheesecake sesame snaps dragée cheesecake."
    }
  }
}
</script>

<style>
.container-about {
  margin: 70px 200px ;
}

h1 {
  text-align: left;
  padding-bottom: 20px;
}
img {
  max-width: 100%;
  vertical-align:middle
}
.col-4 {
  padding-bottom: 50px;
}
</style>
