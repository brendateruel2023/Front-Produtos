<template>
  <div class="container">
    <table class="table table-striped">
      <thead>
        <tr>
          <th>ID</th>
          <th style="width: 22%;">Nome Categoria</th>
          <th style="width: 22%;">Descrição</th>
          <th>Ação</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="category in categories" :key="category.id">
          <td>{{ category.id }}</td>
          <td>{{ category.name }}</td>
          <td>{{ category.description }}</td>
          <td>
            <EditButton />
            <DeleteButton />
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import DeleteButton from '../components/DeleteButton.vue';
import EditButton from '../components/EditButton.vue';

export default {
  name: 'CategoryTable',
  components: {
    DeleteButton,
    EditButton
  },
  data() {
    return {
      categories: [
        { id: 1, name: 'Eletrônicos', description: 'Categoria de produtos eletrônicos' },
        { id: 2, name: 'Móveis', description: 'Categoria de móveis para casa' },
        { id: 3, name: 'Eletrodomésticos', description: 'Categoria de eletrodomésticos' },
        { id: 4, name: 'Roupas', description: 'Categoria de roupas e acessórios' },
        { id: 5, name: 'Esportes', description: 'Categoria de produtos esportivos' }
      ]
    };
  }
};
</script>

<style scoped>
.container {
  margin-top: 60px;
  padding-left: 20px;
}
</style>
