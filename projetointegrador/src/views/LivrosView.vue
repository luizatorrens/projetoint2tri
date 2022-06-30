<script>
import { v4 as uuid } from "uuid";
export default {
  data() {
    return {
      novo_livro: "",
      novo_autor: "",
      nova_categoria: "",
      nova_editora: "",
      livros: [
        {
          id: "f12bc7ce-5ca7-4cbf-ac6e-be3e59cb2862",
          nome_livro: "Diário de um Banana",
          autor: "Jeff Kinney",
          categoria: "Ficção Científica",
          editora: "VR Editora",
        },
        {
          id: "b880659d-5d33-4607-ae19-8a22a738b509",
          nome_livro: "A Seleção",
          autor: "Kiera Cass",
          categoria: "Romance",
          editora: "Seguinte",
        },
        {
          id: "0f97fea6-72ac-4ee0-bf1b-92516d3417e1",
          nome_livro: "A culpa é das Estrelas",
          autor: "John Green",
          categoria: "Romance Drama",
          editora: "Intriseca",
        },
        {
          id: "25c441be-e90a-4847-98a7-0d888e4c981f",
          nome_livro: "Anjo da escuridão",
          autor: "Sidney Sheldon",
          categoria: "Suspense",
          editora: "Arcoíris",
        },
      ],
    };
  },
  methods: {
    salvar() {
      if (this.novo_livro !== "") {
        const novo_id = uuid();
        this.livros.push({
          id: novo_id,
          nome_livro: this.novo_livro,
          autor: this.novo_autor,
          categoria: this.nova_categoria,
          editora: this.nova_editora,
        });
        this.novo_livro = "";
        this.novo_autor = "";
        this.nova_categoria = "";
        this.nova_editora = "";
      }
    },
    excluir(livro) {
      const indice = this.livros.indexOf(livro);
      this.livros.splice(indice, 1);
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
      <h2>Gerencimento de Livros</h2>
    </div>
    <div class="form-input">
      <input
        type="text"
        v-model="novo_livro"
        @keyup.enter="salvar"
        placeholder="Livros"
      />
      <input
        type="text"
        v-model="novo_autor"
        @keyup.enter="salvar"
        placeholder="Autores"
      />
      <input
        type="text"
        v-model="nova_categoria"
        @keyup.enter="salvar"
        placeholder="Categorias"
      />
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
            <td>Livros</td>
            <td>Autores</td>
            <td>Categorias</td>
            <td>Editoras</td>
            <td>Ações</td>
          </tr>
        </thead>
        <tbody>
          <tr v-for="livro in livros" :key="livro.id">
            <td>{{ livro.id }}</td>
            <td>{{ livro.nome_livro }}</td>
            <td>{{ livro.autor }}</td>
            <td>{{ livro.categoria }}</td>
            <td>{{ livro.editora }}</td>

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