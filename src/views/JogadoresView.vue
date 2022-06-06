<template>
  <template>
    <div class="container">
      <div class="title">
        <h2>Gerenciamento de Jogadores</h2>
      </div>
      <div class="form-input">
        <input type="text" />
        <button>Salvar</button>
      </div>
      <div class="list-jogadores">
        <table>
          <thead>
            <tr>
              <th>ID</th>
              <th>Nome</th>
              <th>Time</th>
              <th>Ações</th>
              <th>Time</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>1</td>
              <td>Corinthians</td>
              <td>???</td>
            </tr>
            <tr>
              <td>2</td>
              <td>Palmeiras</td>
              <td>???</td>
            </tr>
            <tr>
              <td>3</td>
              <td>Atlético-MG</td>
              <td>???</td>
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

    .list-jogadores{
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
</template>
