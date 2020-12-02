<template>
  <div>
    <appBar
      @on-home-click="homeBody()"
      @on-carrito-click="carritoBody()"
      @on-favoritos-click="favoritosBody()"
      @on-pedidos-click="pedidosBody()"
    />
    <home
      @on-send-click="addCarrito()"
      @on-sendfav-click="addFavoritos()"
      v-if="body == 'home'"
    />


    <!-- CARRITO DE COMPRAS -->
    <div v-if="body == 'carrito'">
      <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
        <a class="navbar-brand" id="nav">  Carrito de Compras  </a>
      </nav>
      <ul class="list-group" v-if="borrarpedido == true">
        <li class="list-group-item">
          <img id="img-carrito" src="./assets/imagen4.jpg" alt="" />
          <div class="div-text">
            <p id="text">Triple con queso</p>
          </div>
          <p id="cantidad">{{ element }}</p>
          <button
            id="res"
            type="button"
            class="btn btn-warning"
            @click.prevent="restar()"
          >
            -
          </button>
          <button
            id="eliminar"
            type="button"
            class="btn btn-danger"
            @click.prevent="eliminarCarrito()"
          >
            Eliminar
          </button>
          <button
            id="comprar"
            type="button"
            class="btn btn-success"
            @click.prevent="sendToPedidos()"
          >
            Comprar
          </button>
          <button
            id="sum"
            type="button"
            class="btn btn-warning"
            @click.prevent="sumar()"
          >
            +
          </button>
        </li>
      </ul>
    </div>

<!-- FAVORITOS -->
    <div v-if="body == 'favoritos'">
      <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
        <a class="navbar-brand">Favoritos</a>
      </nav>
      <ul class="list-group" v-if="favFalse == true">
        <li class="list-group-item">
          <img id="img-carrito" src="./assets/imagen4.jpg" alt="" />
          <p id="text">{{ favArray }}</p>
          <button
            id="eliminarfav"
            type="button"
            class="btn btn-danger"
            @click.prevent="eliminar()">
            Eiminar de favoritos
          </button>
        </li>
      </ul>
    </div>


<!-- MIS PEDIDOS -->
    <div v-if="body == 'pedidos'">
      <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
        <a class="navbar-brand">Mis pedidos</a>
      </nav>
      <div  v-if="borrarmipedido == true" >
        <ul class="list-group">
          <li class="list-group-item"> Tu pedido de {{ element }} Hamburgesa Triple con queso a sido aceptado
          </li>
          <button
            id="volverpedidos"
            type="button"
            class="btn btn-success"
            @click.prevent="sendTocarrito()">
            Volver al carrito
          </button>
          <button
            id="eliminarpedidos"
            type="button"
            class="btn btn-danger"
            @click.prevent="eliminarpedido()">
            Eliminar Pedido
          </button>
        </ul>
      </div>
    </div>


  </div>
</template>

<script>
import appBar from "./components/AppBar";
import home from "./views/Home";

export default {
  components: { appBar, home },
  name: "app",
  data: () => ({
    body: "home",
    element: 0,
    favArray: "",
    favFalse: true,
    borrarpedido: true,
    borrarmipedido: true,
  }),

  methods: {
    homeBody() {
      this.body = "home";
    },
    pedidosBody() {
      this.body = "pedidos";
    },
    carritoBody() {
      this.body = "carrito";
    },
    favoritosBody() {
      this.body = "favoritos";
    },
    addCarrito() {
      this.body = "carrito";
      this.element = this.element + 1;
      this.borrarpedido = true;
    },
    addFavoritos() {
      if (this.favFalse == false) {
        this.favFalse = true;
      }
      this.favArray = "Triple con queso";
    },
    restar() {
      if (this.element > 1) {
        this.element = this.element - 1;
      }
    },
    sumar() {
      this.element = this.element + 1;
    },
    sendToPedidos() {
      this.body = "pedidos";
      this.borrarmipedido = true;
    },
    sendTocarrito() {
      this.body = "carrito";
    },
    eliminar() {
      this.favFalse = false;
    },
    eliminarCarrito() {
      this.element = 0
      this.borrarpedido = false;
    },
    eliminarpedido() {
      this.element = 0
      this.borrarmipedido = false;
    },
  },
};
</script>


<style>
#img-carrito{
  width: 100%;
}

#text{
  font-size: 23px;
  text-align: center;
  margin-top: 7px;
}
#cantidad {
  color: #ffffff; 
  font-size: 23px; 
  text-align: center; 
  background: #3d4049; 
  padding: 10px; 
  border-radius: 35px 0px 35px 0px;
  margin-top: -13px; 
}

#sum{
  margin-left: 30px;
}

#eliminar{
  margin-left: 35px;
}

#comprar{
  margin-left: 65px;
}

#eliminarfav{
  margin-left: 28%;
}
</style>