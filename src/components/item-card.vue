<template>
  <div>
    <b-card
      :title= "nome"
      :img-src= "image"
      img-alt="Produto"
      img-top
      img-height="300"
      tag="article"
      style="max-width: 20rem;"
      class="mb-2"
      bg-variant="light"
    >
      <b-card-text>{{descricao}}</b-card-text>
      <b-card-text class="font-weight-bold">R$ {{preco}}</b-card-text>

      <b-button href="#" @click.prevent="addToCart(nome)" variant="success">Comprar</b-button>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "item-card",
  props: {
      image: String,
      nome: String,
      descricao: String,
      preco: Number,
  },
  methods: {
      addToCart: function(nomeProduto){
        let itensCart = (localStorage.getItem('itensNoCarrinho') != undefined) ? Number.parseInt(localStorage.getItem('itensNoCarrinho')) : 0;
        localStorage.setItem('itensNoCarrinho',itensCart + 1);

        let produto = [];
        let isProductFinded = false;
        let produtos = localStorage.getItem('product');

        if(produtos != undefined){

            produtos = produtos.split(',');
            produtos.forEach( (produto, index) => {
                if(produtos[index] == nomeProduto){
                    produtos[index + 1] = Number.parseInt(produtos[index + 1]) + 1;
                    localStorage.setItem('product',produtos);
                    isProductFinded = true;
                }
            });

            if(!isProductFinded){
                produtos.push(nomeProduto);
                produtos.push(1);
                localStorage.setItem('product',produtos);
            }

        } else {
            produto.push(nomeProduto);
            produto.push(1);
            localStorage.setItem('product',produto);
        }       

        this.$emit('update-cart');
    }
  }
};
</script>

<style scoped>
.size {
  height: 26rem;
}

</style>
