<template>
<!-- NAVBAR -->
  <div>
    <nav class="navbar navbar-expand-md bg-dark navbar-dark">
      <a @click.prevent="homeClick" class="navbar-brand" href="#">PEDIYA</a>
      <button
        class="navbar-toggler"
        type="button"
        data-toggle="collapse"
        data-target="#collapsibleNavbar">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="collapsibleNavbar">
        <ul class="navbar-nav">
          <li class="nav-item">
            <button
              @click.prevent="homeClick"
              type="button"
              id="btn-nav"
              class="btn btn-outline-light"
            >
            <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAAj0lEQVRIie2TzQ2AIAxGHYGR2P+CG+gIbvC8oGm0YvlLjPolPRDoe4SUYfhMAAeEWK4XfEs7yQE+xmojUeAuVr1Egx/2yiUpeLXEAi+W5MCzJcoomt819qZHWNwCACtc9MuE3oLx9qBYe2DinAnwV305glmB75IWArXReu4XPFOwUJ7ZIvCkR/MSjvgX78kK+fDO7Z9imtUAAAAASUVORK5CYII="/> Home
            </button>
          </li>
          <li class="nav-item">
            <button
              @click.prevent="carritoClick"
              type="button"
              id="btn-nav"
              class="btn btn-outline-light">
              <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAABQ0lEQVRIS9WU3TFEQRCFvxMBIkAEiAARIAK88oAIEAEe1isyIAKbASIgA0RwVKt7t2Z3Z+7drbtbSj9NVff0+enpEXMOzbk//wfA9jVwUjsi6Zf8TBTY3gKeU7tnDfAI7ABnkkLJIDorsL0CvFcdlyR9ZQFsvwJrHV7Vg6SD0fsDBbY/gOUOABuSguRQpAAXwDmQZZIDth2M74A3Seu5mhSg9jI8XB31sgBQ23oo6b4RIJK2+8AmULxQN7EdjF+Ab0mLJWuHXlEiuS9pu2ketoPxPnAj6XRSgGASw16obIrzWNiOus8qEXZm67KbnDC7lBSDzwEE4yvgSdJuk9KxRcutfUODPUmxxcXIbvKES1d8mila56+ibTFLCnrAEXAr6ThtYruYa92D5I27Ptff7iS5aQDmq6DN12nyfzPkaRi21f4Ab3d/GTSFNJwAAAAASUVORK5CYII="/>
              Carrito de Compras
            </button>
          </li>
          <li class="nav-item">
            <button type="button" id="btn-nav" class="btn btn-outline-light " @click.prevent="favoritosClick">
              <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAA6klEQVRIS8WV2RHCMAwFVx3QCVABUAlQGaESoIOkEzowI0bJOIdj5zDkz9H4rSXryULmTzLr8x+AgwtwBo6W4RMoBO66jsX9qrQycLABHsAuULrS/o/FTwLven8XoALbhfdSCux7AEv7tlC83n4VKHTRZOBA63xYCfASuz8f4FYS/8qIHf6ngOwl0t7Pd8lmoDXatBLPR0NG01LN9UKl7g8azbJQN8+B9MRbPvBb1EbGFMigeBAwMZOg+CggETIqHgVEIFHxJEAAkiSeDOhAdNlqxbEZNunJtO7SQdY8KLEBOQkQExuKZwd8ABshRBmu6Hx7AAAAAElFTkSuQmCC"/>
              Favoritos
            </button>
          </li>
          <li class="nav-item">
            <button type="button" id="btn-nav" class="btn btn-outline-light " @click.prevent="pedidosClick">
              <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABgAAAAYCAYAAADgdz34AAAAYElEQVRIie2R0QnAIAwFHSGjdaN2w7rR+fM+ShE0EEEh9+9dEktJkvPAwZ6B89n2DwAD7pAtO0MZ8Kr7rJRXwEYPhicBLol98pmA5Ejsk8+gqeunGyfvROLlv8gaeRJKAxkgaOwM7u7pAAAAAElFTkSuQmCC"/>
               Mis pedidos
            </button>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>


<script>
export default {
  name: "appBar",
  methods: {
    homeClick() {
      this.$emit("on-home-click");
    },
    carritoClick() {
      this.$emit("on-carrito-click");
    },
    favoritosClick() {
      this.$emit("on-favoritos-click");
    },
    pedidosClick() {
      this.$emit("on-pedidos-click");
    },
  },
};
</script>


<style>
#btn-nav{
  background-color: transparent;
  border: 0px solid;

}
</style>