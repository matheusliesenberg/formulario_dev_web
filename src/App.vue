<template>
  <h1>{{ titulo }}</h1>
  <div class="container d-flex flex-row gap-3">
    <div class="formulario">
      <h2>Cadastro de usuario</h2>

      <div class="form-group">
        <label for="">Nome:</label>
        <input class="form-control" type="text" v-model="usuario.nome" />
      </div>

      <div class="form-group">
        <label for="">E-mail:</label>
        <input class="form-control" type="text" v-model="usuario.email" />
      </div>

      <div class="form-group">
        <label for="">Data de nascismento:</label>
        <input class="form-control" type="date" v-model="usuario.Data" />
      </div>

      <div class="form-group">
        <label for="">Endereço:</label>
        <input class="form-control" type="text" v-model="usuario.endereco" />
      </div>

      <div class="form-group">
        <label for="">Cidade:</label>
        <input class="form-control" type="text" v-model="usuario.Cidade" />
      </div>

      <div class="form-group">
        <label for="">Hobbies:</label>
        <input class="form-control" type="text" v-model="usuario.Hobbies" />
      </div>

      <div class="form-group">
        <label for="">Biografia</label>
        <input class="form-control" type="text" v-model="usuario.Biografia" />
      </div>

      <div class="select">
        <div class="form-group">
          <label for="">Estados:</label>
          <select name="estado" id="estado">
            <option value="AC">Acre</option>
            <option value="AL">Alagoas</option>
            <option value="AP">Amapá</option>
            <option value="AM">Amazonas</option>
            <option value="BA">Bahia</option>
            <option value="CE">Ceará</option>
            <option value="DF">Distrito Federal</option>
            <option value="ES">Espírito Santo</option>
            <option value="GO">Goiás</option>
            <option value="MA">Maranhão</option>
            <option value="MT">Mato Grosso</option>
            <option value="MS">Mato Grosso do Sul</option>
            <option value="MG">Minas Gerais</option>
            <option value="PA">Pará</option>
            <option value="PB">Paraíba</option>
            <option value="PR">Paraná</option>
            <option value="PE">Pernambuco</option>
            <option value="PI">Piauí</option>
            <option value="RJ">Rio de Janeiro</option>
            <option value="RN">Rio Grande do Norte</option>
            <option value="RS">Rio Grande do Sul</option>
            <option value="RO">Rondônia</option>
            <option value="RR">Roraima</option>
            <option value="SC">Santa Catarina</option>
            <option value="SP">São Paulo</option>
            <option value="SE">Sergipe</option>
            <option value="TO">Tocantins</option>
          </select>
        </div>
      </div>
      <button type="button" class="button" @click="mostrarResultado = !mostrarResultado">
        Mostrar
      </button>
    </div>

    <div v-if="mostrarResultado" class="resultado">
      <h2>Dados do usuario</h2>
      <p>Nome: {{ usuario.nome }}</p>
      <p>E-mail {{ formatarPreco(usuario.email) }}</p>
      <p>Data de nascimento: {{ usuario.Data }}</p>
      <p>Endereço: {{ usuario.endereco }}</p>
      <p>Cidade: {{ usuario.Cidade }}</p>
      <P>Estado: {{ usuario.estados }}</P>
      <p>Hobbies: {{ usuario.Hobbies }}</p>
      <p>Biografia: {{ usuario.Biografia }}</p>
    </div>
  </div>

  <div class="altera-titulo">
    <label>Informe um novo título </label>
    <input class="form-control" type="text" v-model="titulo" />
  </div>
</template>

<style scoped>
.select {
  margin-top: 7px;
  border-radius: 10000px;
}
.button {
  border-radius: 25px;
  background-color: black;
  margin-top: 20px;
  margin-left: 8.5rem;
  color: rgb(255, 255, 255);
  cursor: pointer;
  border-color: blue;
  padding: 5px 10px;
  display: inline-block;
  transition: background-color 0.5s;
  align-items: center;
}
.button:hover {
  background-color: rgb(20, 0, 201);
}

.formulario,
.resultado {
  width: 48%;
  border-radius: 25px;
  padding: 20px;
}

.formulario {
  color: antiquewhite;
  background-color: #000000;
  align-items: center;
  border: 10px;
  border-color: blue;
}

.resultado {
  background-color: #98e0aa;
}

.altera-titulo {
  background-color: #98e0aa;
  margin: 1rem 2rem;
  border-radius: 20px;
  padding: 0.75rem;
}
</style>

<script setup>
import { reactive, ref } from 'vue'

const titulo = ref('Oi VueJs!')
const mostrarResultado = ref(false)

const estados = []

const usuario = reactive({
  nome: '',
  email: '',
  Data: 0,
  endereço: '',
  Cidade: '',
  estados: '',
  Biografia: ''
})

function formatarPreco(email) {
  return `${email}`
}
</script>
