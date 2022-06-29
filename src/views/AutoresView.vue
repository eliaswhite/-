<script>
import { v4 as uuid4 } from "uuid";
export default {
  data() {
    return {
      autores: [
        {
          id: "7c9e22c2-b2f4-45ba-80d9-5d702bf357ec",
          nome: "Autor 1",
          livro_id: "ghghrfh",
        },
        {
          id: "3dbf86f0-f4b3-436b-aae7-3a6c043547bb",
          nome: "Autor 2",
          livro_id: "ghghrfh",
        },
        {
          id: "d53d669e-1143-48b6-8169-43156f646b24",
          nome: "Autor 3",
          livro_id: "ghghrfh",
        },
      ],
      novo_autor: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuid4();
      this.autores.push({
        id: novo_id,
        nome: this.novo_autor,
      });
    },
  },
};
</script>
<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de Autores</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_livro_id" />
      <input type="text" v-model="novo_autor" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-jogadores">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Livro ID</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="autor in autores" :key="autor.id">
            <td>{{ autor.id }}</td>
            <td>{{ autor.nome }}</td>
            <td>{{ autor.livro_id }}</td>
            <td>
              <button @click="excluir(autor)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style>
.title {
  text-align: center;
  margin: 0rem 0;
}

.form-input {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}

.form-input input {
  width: 50%;
  padding: 0.5rem;
  border: 1px ridge #ccc;
  border-radius: 10px;
}

.form-input button {
  padding: 0.5rem;
  border: 1px double rgb(72, 255, 0);
  border-radius: 10px;
  background-color: black;
  color: #ccc;
  font-weight: bold;
}

.list-times {
  display: flex;
  justify-content: center;
}

table {
  width: 50%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid black;
  font-size: 1.1rem;
}

table thead {
  background-color: darkblue;
  color: white;
}

table tbody tr {
  text-align: center;
}

table tbody tr:nth-child(odd) {
  background-color: cadetblue;
}
</style>
