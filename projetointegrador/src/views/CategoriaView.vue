<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      nova_categoria: "",
      categorias: [
        { id: "f12bc7ce-5ca7-4cbf-ac6e-be3e59cb2862", categoria: "Romance" },
        { id: "b880659d-5d33-4607-ae19-8a22a738b509", categoria: "Suspense" },
        { id: "0f97fea6-72ac-4ee0-bf1b-92516d3417e1", categoria: "Ficção" },
        { id: "25c441be-e90a-4847-98a7-0d888e4c981f", categoria: "Drama" },
      ],
    };
  },
  methods: {
    salvar() {
      if (this.nova_categoria !== "") {
        const novo_id = uuid();
        this.categorias.push({
          id: novo_id,
          categoria: this.nova_categoria,
        });
        this.nova_categoria = "";
      }
    },
    excluir(categoria) {
      const indice = this.categorias.indexOf(categoria);
      this.categorias.splice(indice, 1);
    },
    alerta() {
      alert("Ok!");
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerencimento de Categorias</h2>
    </div>
    <div class="form-input">
      <input
        type="text"
        v-model="nova_categoria"
        @keyup.enter="salvar"
        placeholder="Categoria"
      />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-items">
      <table>
        <thead>
          <tr>
            <td>ID</td>
            <td>Categorias</td>
            <td>Ações</td>
          </tr>
        </thead>
        <tbody>
          <tr v-for="categoria in categorias" :key="categoria.id">
            <td>{{ categoria.id }}</td>
            <td>{{ categoria.categoria }}</td>
            <td>
              <button @click="alerta(livro)">Editar</button>
              <button @click="excluir(livro)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>
<style></style>
