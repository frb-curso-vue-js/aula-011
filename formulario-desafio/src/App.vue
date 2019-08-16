<template>
	<div id="app">
		<h1>Formulário Desafio</h1>
		<div class="conteudo">
			<!-- <form class="painel" v-if="!submitted"> -->
			<form class="painel">
				<div class="cabecalho">Formulário</div>
				<!-- Exercicio 01 -->
				<!-- Criar uma formulário de registro -->
				<NomeCompleto :value="nomeCompleto" v-model="nomeCompleto" />
				<Rotulo nome="Email">
					<input type="text" v-model="email">
				</Rotulo>
				<Rotulo nome="Senha">
					<input type="password" v-model="senha">
				</Rotulo>
				<Rotulo nome="Armazenar dados?">
					<input type="checkbox" v-model="armazenar">
				</Rotulo>
				
				<!-- Nome completo (Nome e Sobrenome) -->
				<!-- Email -->
				<!-- Senha -->
				<!-- Armazenar Dados? (Sim/Não) -->

				<!-- Exercicio 02 -->
				<!-- Só mostrar o fomulário de não tiver sido submetido -->
				<!-- Mostrar a área de Resultado apenas quando o formulário for submetido -->
				
				<!-- Exercicio 03 -->
				<!-- Crie um componente personalizado NomeCompleto -->
				<!-- Esse componente deve receber Nome e Sobrenome -->
				<button @click.prevent="enviar">Enviar</button>
			</form>
			<!-- <div class="painel" v-else> -->
			<div class="painel">
				<div class="cabecalho">Resultado</div>
			<ul>
				<li>Nome: {{nomeCompleto.nome}}</li>
				<li>Sobrenome: {{nomeCompleto.sobrenome}}</li>
				<li>E-mail: {{email}}</li>
				<li>Senha: {{senha}}</li>
				<li>Armazenar: {{armazenar ? 'Sim' : 'Não'}}</li>
			</ul>
			</div>
		</div>
	</div>
</template>

<script>
import Rotulo from './components/Rotulo.vue'
import NomeCompleto from './components/NomeCompleto.vue'

export default {
	name: 'app',
	data() {
		return {
			armazenar: false,
			email: '',
			senha: '',
			submitted: false,
			nomeCompleto: {
				nome: 'Kikito',
				sobrenome: 'Kito'
			},
		}
	},
	methods : {
		enviar() {
			this.submitted = true
		}
	},
	components: { Rotulo, NomeCompleto }
}
</script>

<style>

body {
	background-color: #ECECEC;
}

#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;

	display: flex;
	flex-direction: column;
}

.conteudo {
	display: flex;
}

.painel {
	flex: 1;
	background: #FFF;
	margin: 0px 10px;
	padding: 20px;
	border: 1px solid #AAA;
	border-radius: 5px;
}

.painel .cabecalho {
	width: 100%;
	background-color: #DDD;
	padding: 10px 0px;
	border-radius: 5px;
	font-size: 1.4rem;
}

#app form button {
	float: right;
	margin: 10px 0px;
	padding: 10px 20px;
	font-size: 1.4rem;
	border-radius: 5px;
	color: #FFF;
	background-color: #2196F3;
}

#app h1 {
	font-weight: 200;
	margin: 20px;
	padding: 0;
}

.mr-4 {
	margin-right: 40px;
}
</style>
