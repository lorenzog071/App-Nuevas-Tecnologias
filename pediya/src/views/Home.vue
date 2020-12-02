<template>
  <div>
    <div class="ca">
      <div id="demo" class="carousel slide" data-ride="carousel">
        <div class="carousel-inner">
          <div class="carousel-item active" id="imagen">
            <img src="../assets/imagen1.jpg" alt="" />
          </div>
          <div class="carousel-item">
            <img src="../assets/imagen2.jpg" class="imagen" alt="" />
          </div>
          <div class="carousel-item">
            <img src="../assets/imagen3.jpg" alt="" />
          </div>
        </div>
        <a class="carousel-control-prev" href="#demo" data-slide="prev">
        <span class="carousel-control-prev-icon"></span>
        </a>
        <a class="carousel-control-next" href="#demo" data-slide="next">
        <span class="carousel-control-next-icon"></span>
        </a>
      </div>
    </div>
    <br/>

    <div class="container">
      <div class="card">
        <img src="../assets/imagen4.jpg" alt="" />
        <div class="card-body">
          <button @click.prevent="sendToFavoritos()" id="favorito" type="button" class="btn btn-danger" >
            <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAABKklEQVRIS9WV4W3CQAyFPyagI7QTQCconaSwQUdhA+gkLRu0E7QjwASgV9mRc0pyBikg7s/p7Nx79rN9mTDymoyMz80IlsAbsLAMv4At8GHnmr8RpszgAfgE5j3SfZt9yP8K7P1+SSCAGXAA3gFFrqVM1sDUzu6PhO6X7bmLQGlvDPwxRmEfK7tI2EQZ/H8WxMokbRVZl1+AxnlBh3mQO69flOhogE+AIrlkKfNfu/iPfVWC0SVy/VQ8yVQWsSaZmkDyaO8ssgC8TbW3+rmCHufnJ85R16BJKs1ClqQE18z0DpoC9X7PkAyCl10UVciQVMGHCGqZpMBrBH0ksvuDqIK2NC+bIfM/KOUShl7TKngmAw8oksiWAj+HIMrlz3dqEDMS1SZ40H//BCd7O1cZtSzGCwAAAABJRU5ErkJggg=="
            />
          </button>
          <h4 class="card-title">Triple con Queso</h4>
          <p class="card-text">Tres carnes de 100gr mas papas fritas</p>
          <button
            @click.prevent="sendToCarrito()"
            type="button"
            class="btn btn-success">
            Agregar al carrito
          </button>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "home",
  data: () => ({
  }),
  methods: {
    sendToCarrito() {
      this.$emit("on-send-click");
    },
    sendToFavoritos() {
      this.$emit("on-sendfav-click");
    },
  },
};
</script>


<style>
  #favorito{
    margin-top: -60px;
    margin-left: 280px;
    padding: 5px 12px;
    border-radius: 35px;
    font-size: 24px;
    line-height: 1.33;
  }
</style>







          