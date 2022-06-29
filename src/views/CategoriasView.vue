<script>
import { v4 as uuid4 } from "uuid";
export default {
  data() {
    return {
      categorias: [
        { id: "7c9e22c2-b2f4-45ba-80d9-5d702bf357ec", descrição: "Categoria 1" },
        { id: "3dbf86f0-f4b3-436b-aae7-3a6c043547bb", descrição: "Categoria 2" },
        { id: "d53d669e-1143-48b6-8169-43156f646b24", descrição: "Categoria 3" },
      ],
      novo_editora: "",
    };
  },
  methods: {
    salvar() {
      if (this.novo_categoria!== "") {
        const novo_id = uuid4();
        this.categorias.push({
          id: novo_id,
          descrição: this.novo_categoria,
        });
        this.novo_categoria = "";
      }
    },
    excluir(categoria) {
      const indice = this.categorias.indexOf(categoria);
      this.categorias.splice(indice, 1);
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de categorias</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_categoria" @keydown.enter="salvar" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-categorias">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Descrição</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="categoria in categorias" :key="categoria.id">
            <td>{{ categoria.id }}</td>
            <td>{{ categoria.descrição }}</td>
            <td>
              <button @click="excluir(categoria)">Excluir</button>
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
  margin-left: 1%;
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