<template>
  <div class="container-fluid bg-semi-light full-screen-size">
    <cabecalho :usuario="usuario" :badge="badge"/>
    <br>

    <div class="container">
      <div class="row mb-3" v-for="i in 3" :key="i">
        <div class="col-4" v-for="produto in produtos" :key="produto">
          <itemCard :image="produto.imagem" :nome="produto.nome" :preco="produto.preco" :descricao="produto.descricao"  @update-cart="updateCart"/>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import itemCard from "@/components/item-card.vue";
import cabecalho from "@/components/cabecalho.vue";

export default {
  name: "Home",
  components: {
    itemCard,
    cabecalho
  },
  data: function(){
    return{
      usuario: 'XPTO',
      badge: 0,
      produtos: [
        {
          imagem: 'https://www.brandability.co.za/wp-content/uploads/2017/07/180g-Barron-T-shirt-dove-grey.jpg',
          nome: 'Camiseta cinza',
          descricao: 'Camiseta originária da London Week Out Fall 2019',
          preco: 10
        },
        {
          imagem: 'https://5.imimg.com/data5/VT/DS/MY-17368652/plain-round-neck-tshirt-500x500.jpg',
          nome: 'Camiseta branca',
          descricao: 'Camiseta originária do Canada Out Winter 2019',
          preco: 20
        },
        {
          imagem: 'https://images-na.ssl-images-amazon.com/images/I/71f9eHfa0cL._UX522_.jpg',
          nome: 'Camiseta amarela',
          descricao: 'Camiseta originária da Argelia Out Summer 2019',
          preco: 30
        }
      ]
    }
  },
  methods: {
    updateCart: function(){
      this.badge += 1;
    }
  }
};
</script>
<style scoped>
.full-screen-size {
  height: auto;
}
.pt-10 {
  padding-top: 18rem;
}

.bg-semi-light {
  background-color: rgb(236, 236, 236);
}
.blur-3{
  filter: blur(5px) brightness(0.7);
}
.ml-4-5{
  margin-left: 1.8rem;
}
.container-fluid {
    width: 100%;
    padding: 0;
    margin-right: auto;
    margin-left: auto;
}
</style>
