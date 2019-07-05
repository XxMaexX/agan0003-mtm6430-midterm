<template>
  <div class="home">
    <h1>ღ Welcome to My Candy Wonderland ღ</h1>
    <div class="image">
      <div class="main">
        <img src="../assets/candies-colorful-colourful.jpg">
      </div>
    <div class="container">
      <p> {{ maincandy1 }} </p>
      <p> {{ maincandy2 }} </p>
  </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      // returning text in required area
      maincandy1: "Cupcake ipsum dolor. Sit amet cake lemon drops cotton candy macaroon gummies oat cake soufflé. Tart dessert croissant donut. Tiramisu sugar plum pudding gingerbread biscuit tootsie roll sesame snaps. Dragée pie topping toffee tart tootsie roll halvah. Chocolate cheesecake marshmallow cotton candy danish sesame snaps. Oat cake chupa chups apple pie lollipop gummi bears brownie candy canes tiramisu. Lollipop danish bear claw gummi bears lemon drops cotton candy cake gummi bears. Cotton candy sweet roll cake sesame snaps icing dragée cookie pie donut. Candy canes muffin jelly-o dragée dessert tart toffee cotton candy. Tootsie roll bear claw lemon drops soufflé. Sugar plum danish muffin pudding chocolate cake powder jelly beans. Pie halvah caramels.",
      maincandy2: "Bear claw muffin cheesecake gummies toffee soufflé cake dragée macaroon. Icing icing tiramisu. Cookie caramels icing jelly beans topping. Candy candy canes chupa chups cupcake tootsie roll sweet halvah liquorice. Gummi bears donut brownie gummies chupa chups liquorice tootsie roll pie ice cream. Jelly caramels cheesecake pastry icing. Candy jelly-o gummi bears pie cotton candy. Sweet roll chupa chups muffin gingerbread marshmallow cookie pie. Apple pie jelly-o macaroon sugar plum cheesecake icing bear claw. Caramels cupcake apple pie halvah cake gummi bears bear claw. Sugar plum cake jelly beans. Sugar plum topping gummi bears cupcake caramels dragée gingerbread bear claw. Icing marzipan jelly-o chupa chups cupcake candy canes icing candy. "
    }
  }
}
</script>

<style>
.home h1 {
  display: flex;
  padding-left: 50px;
  padding-top: 30px;
}
.image {
  display: flex;
}
.main {
  max-width: 45%;
  max-height: 45%;
  padding: 45px;
}
.container {
  display: block;
  box-sizing: border-box;
  padding: 35px;
}
.image .container {
  vertical-align: middle;
}

p {
  font-size: 20px;
  text-align: left;
}
</style>
