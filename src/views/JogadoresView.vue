<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      times: [
        { id: "4dfadc62-3011-48a9-a384-53cbc062b0b2", nome: "Time 1" },
        { id: "6fe0c8e2-619b-4c46-b92b-e1ca7a3b970c", nome: "TIme 2" },
        { id: "9e3a44e1-bceb-4786-a1fd-38c5a76a7745", nome: "Time 3" },
      ],
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.times.push({
        id: novo_id,
        nome: this.novo_jogador,
        time: this.novo_time,
      });
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de Jogadores</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" />
      <input type="text" v-model="novo_jogador" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-times">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>{{ time.id }}</td>
            <td>{{ time.nome }}</td>
            <td>???</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <RouterView />
</template>
