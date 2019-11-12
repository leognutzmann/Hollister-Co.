<template>
  <div class="container-fluid bg-semi-light full-screen-size">
    <div class="row">
      <div class="col-4 offset-2 pt-10">
        <img :src="logo" :height="logoSize" class="ml-4-5">
        <Enter />
      </div>
      <div class="col-6 blur-3">
        <img :src="imageSource" :height="size" >
      </div>
    </div>
  </div>
</template>

<script>
import Enter from "@/components/enter.vue";

export default {
  name: "Login",
  components: {
    Enter
  },
  data: function(){
    return{
      imageSource: require('@/assets/imagem.jpg'),
      size: '1300',
      logo: require('@/assets/logo.png'),
      logoSize: '150'
    }
  }
};
</script>
<style scoped>
.full-screen-size {
  height: 100vh;
  overflow: hidden;
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
</style>
