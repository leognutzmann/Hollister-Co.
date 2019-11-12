<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#"><img src="@/assets/logo.png" width="80"></b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0 btn-success mr-5" type="submit">Pesquisar</b-button>
          </b-nav-form>

          <b-nav-item href="#" class="mr-5">Carrinho <b-badge variant="light">{{badge}}</b-badge> </b-nav-item>

          <b-nav-item-dropdown right>
            <!-- Using 'button-content' slot -->
            <template v-slot:button-content>
              <em>{{usuario}}</em>
            </template>
            <b-dropdown-item href="#">Meu perfil</b-dropdown-item>
            <b-dropdown-item href="#">Sair</b-dropdown-item>
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "cabecalho",
  props: {
    usuario: String,
    badge: Number
  },
  mounted: function(){
    this.badge = localStorage.getItem("itensNoCarrinho");
  }
  
};
</script>

<style scoped>

</style>
