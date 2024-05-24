<template>
  <div class="container">
    <table class="table table-striped">
      <thead>
        <tr>
          <th>ID</th>
          <th style="width: 22%;">Nome Produto</th>
          <th style="width: 22%;">Preço</th>
          <th>Quantidade</th>
          <th>Categoria</th>
          <th>Ação</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="product in products" :key="product.id">
          <td>{{ product.id }}</td>
          <td>{{ product.name }}</td>
          <td>{{ product.price }}</td>
          <td>{{ product.quantity }}</td>
          <td>{{ product.category }}</td>
          <td>
            <EditeButton />
            <DeleteButton />
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import DeleteButton from '../components/DeleteButton.vue';
import EditeButton from '../components/EditButton.vue';

export default {
  name: 'ProductTable',
  components: {
    DeleteButton,
    EditeButton
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Sansung Galaxy S23', price: '4300,00', quantity: 10, category: 'Eletronicos' },
        { id: 2, name: 'Notebook Acer Nitro 5', price: '6000,00', quantity: 15, category: 'Eletronicos' },
        { id: 3, name: 'Sofá', price: '900,00', quantity: 5, category: 'Móveis' },
        { id: 4, name: 'Geladeira', price: '6500,00', quantity: 6, category: 'Eletrodomésticos' },
        { id: 5, name: 'Cadeira', price: '500,00', quantity: 2, category: 'Móveis' }
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
 