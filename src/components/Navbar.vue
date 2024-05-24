<template>
  <nav class="navbar navbar-dark bg-dark fixed-top">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Mais Produtos</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasDarkNavbar"
        aria-controls="offcanvasDarkNavbar" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="offcanvas offcanvas-end text-bg-dark" tabindex="-1" id="offcanvasDarkNavbar"
        aria-labelledby="offcanvasDarkNavbarLabel">
        <div class="offcanvas-header">
          <h5 class="offcanvas-title" id="offcanvasDarkNavbarLabel">Mais Produtos</h5>
          <button type="button" class="btn-close btn-close-white" data-bs-dismiss="offcanvas"
            aria-label="Close"></button>
        </div>
        <div class="offcanvas-body">
          <ul class="navbar-nav justify-content-end flex-grow-1 pe-3">
            <li class="nav-item">
              <RouterLink to="/" class="nav-link active" aria-current="page" href="#">Início</RouterLink>
            </li>
            <li class="nav-item">
              <RouterLink to="/addproduct" class="nav-link" href="#">Adicionar Produto</RouterLink>
            </li>
            <li class="nav-item">
              <RouterLink to="/addcategorie" class="nav-link" href="#">Adicionar Categoria</RouterLink>
            </li>
            <li class="nav-item">
              <RouterLink to="/tablecategories" class="nav-link" href="#">Tabela de Categorias</RouterLink>
            </li>
            <li class="nav-item dropdown">
              <RouterLink class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown"
                aria-expanded="false">
                Categorias
              </RouterLink>
              <ul class="dropdown-menu dropdown-menu-dark p-2">
                <input class="form-control bg-dark w-100 text-light" v-model="searchCategories">
                <li v-for="category in filteredCate">
                  <a class="dropdown-item" href="#">
                    {{ category.name }}
                  </a>
                </li>
                <li><a class="dropdown-item" href="#">Mais Categorias</a></li>
              </ul>
            </li>
          </ul>
          <form class="d-flex mt-3" role="search">
            <input class="form-control me-2" type="search" placeholder="Nome Produto" aria-label="Search">
            <button class="btn btn-success" type="submit">Pesquisar</button>
          </form>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { computed, reactive, ref } from 'vue';

const searchCategories = ref("");
const categories = reactive(
  [
    {
      name: "Eletronicos"
    },
    {
      name: "Eletrodomésticos"
    },
    {
      name: "Abobora"
    }
  ]
);

const filteredCate = computed(() => {
  return categories.filter((category) => {
    return category.name.toLowerCase().includes(searchCategories.value);
  });
});


</script>

<style></style>
