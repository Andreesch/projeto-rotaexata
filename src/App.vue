<template>
  <div id="app">
    <h3>Cadastro para vacinação</h3>

    <div>
      <form action="">
        <label>Nome completo</label><br>
        <!-- ligação com v-model -->
        <input type="text" v-model="nomeCompleto"><br>

        <label for="">E-mail</label><br>
        <input type="text" v-model="email"><br>

        <label>CPF</label><br>
        <input type="number" v-model="cpf"><br>

        <label>Data de nascimento</label><br>
        <input type="text" v-model="dataNasc"><br>

        <label>Senha</label><br>
        <input type="password" v-model="senha"><br>

        <div id="caixaSexo">
          <label for="">Informe seu sexo:</label>
          <span><input type="radio" value="masc" v-model="sexo">Masculino</span>
          <span><input type="radio" value="femi" v-model="sexo">Feminino</span>
          <span><input type="radio" value="outros" v-model="sexo">Outros</span>
        </div>
        <!-- checkbox e text area -->

        <!-- ideia para api estados -->

        <!-- Botão cadastro / prevent não irá atualizar  -->
        <div id="btnCadastrar">
          <button type="submit" @click.prevent="cadastrar">Cadastrar</button>
        </div>
      </form>
    </div>

    <hr>

    <!-- Div de cadastro / so será acionada quando o valor for TRUE -->
    <div class="item" v-show="cadastro">
      <h2>Usuário cadastrado</h2>
      <label for="">Nome: {{nomeCompleto}}</label><br>
      <label for="">E-mail: {{email}}</label><br>
      <label for="">CPF: {{cpf}}</label><br>
      <label for="">Data de nascimento: {{dataNasc}}</label><br>
      <label for="">Senha: {{senha}}</label><br>
      <label for="">Sexo: {{sexo}}</label>
      
    </div>

  </div>
</template>

<script>


export default {
  name: 'App',

  //cadastro usuario
  data(){
    return{
      nomeCompleto: '',
      email: '',
      cpf: '',
      dataNasc: '',
      senha: '',
      sexo: 'masc',
      //envio do form
      cadastro: false
    }
    
  },
  //método para envio do form
  methods:{
    cadastrar(){
      alert('Cadastro realizado com sucesso :)')
      this.cadastro = true;
    }
  }
}
</script>

<style scoped>
  form{
    display: flex;
    flex-direction: column;
  }
</style>
