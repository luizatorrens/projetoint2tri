<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      nova_editora: "",
      editoras: [
        {
          id: "f12bc7ce-5ca7-4cbf-ac6e-be3e59cb2862",
          name: "Arco iris",
        },
        {
          id: "b880659d-5d33-4607-ae19-8a22a738b509",
          name: "Azul",
        },
        {
          id: "0f97fea6-72ac-4ee0-bf1b-92516d3417e1",
          name: "Rocco",
        },
        {
          id: "25c441be-e90a-4847-98a7-0d888e4c981f",
          name: "Página",
        },
      ],
    };
  },
  methods: {
    salvar() {
      if (this.nova_editora !== "") {
        const novo_id = uuid();
        this.editoras.push({
          id: novo_id,
          name: this.nova_editora,
        });
        this.nova_editora = "";
      }
    },
    excluir(editora) {
      const indice = this.editoras.indexOf(editora);
      this.editoras.splice(indice, 1);
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
      <h2>Gerencimento de Editoras</h2>
    </div>
    <div class="form-input">
      <input
        type="text"
        v-model="nova_editora"
        @keyup.enter="salvar"
        placeholder="Editoras"
      />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-items">
      <table>
        <thead>
          <tr>
            <td>ID</td>
            <td>Editoras</td>
            <td>Ações</td>
          </tr>
        </thead>
        <tbody>
          <tr v-for="editora in editoras" :key="editora.id">
            <td>{{ editora.id }}</td>
            <td>{{ editora.name }}</td>
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