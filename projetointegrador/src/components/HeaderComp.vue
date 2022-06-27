<template>
  <header class="menu-superior">
    <div class="menu-esquerdo">
      <span> <RouterLink to="/autor">Autor</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/editora">Editora</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/categoria">Categoria</RouterLink> </span>
      <span>|</span>
      <span> <RouterLink to="/livros">Livros</RouterLink> </span>
    </div>
  </header>
</template>

<style>
header span {
  padding: 0 20px;
}
.menu-superior {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
