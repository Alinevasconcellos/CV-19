# CV-19
Quiz CV-19<!doctype html>
<html>
<head>
	<meta charset="utf-8" />
	<title>teste.html</title>
	<meta name = "viewport" content="width=device-width, initial-scale=1">
	<style type="text/css">

 body{ margin: 0;
 	font-size: 16px;
 	background-color: #556B2F;
 	font-family: cursive;
 	font-weight: 400;


 }

*{
	box-sizing: border-box;
	margin: 0;
	padding: 0;
	outline: none;

}


.custom-box{
	max-width: 700px;
	background-color: #ffffff;
	margin: 40px auto;
	padding: 30px;
	border-radius: 10px;
}	




.custom-box.hide{
display: none;
}
.home-box h3{
	font-size: 18px;
	color: #228b22;
	font-weight: 500;
	margin-bottom: 15px;
	line-height: 25px;
}

.home-box p{
	font-size: 16px;
	margin-bottom: 10px;
	line-height: 22px;
	color: #228b22;
	font-weight: 400;
}

.home-box p span{
	font-weight: 500;
}

.home-box .btn{
	margin-top: 10px;
}

.btn{
	padding: 15px 45px;
	background-color: #228b22;
	color: #ffffff;
	border: :none;
	border-radius: 10px;
	font-family: cursive;
 	font-size: 15px;
 	display: inline-block;
}

.quiz-box .numero-questao{
	font-size :18px;
	color: #228b22;
	font-weight: 600;
	border-bottom: 1px solid #cccccc;
	padding-bottom: 10px;
	line-height: 25px;
}

.quiz-box .texto-quest{
	line-height: 28px;
	font-weight: 400;
	padding: 10px 0;
	margin: 0;
}

.quiz-box .opcoes .opcao{
	padding: 15px;
	font-size: 16px;
	line-height: 22px;
	cursor: pointer;
	background-color:#cccccc;
	color:#000000;
	border-radius: 5px;
	margin-bottom: 10px;
	cursor: pointer;
	text-transform: capitalize;
	opacity: 0;
	animation: fadeIn 0.3s ease forwards;
	position: relative; 
    overflow: hidden;
	
}
 .quiz-box .opcoes .opcao.errada::before{
content: '';
position: absolute;
left: 0;
top: 0;
height: 100%;
width :100%;
background-color: red;
z-index: -1;
}

.quiz-box .opcoes .opcao.errada{
	color: #ffffff;
}

.quiz-box .opcoes .opcao.correta::before{
content: '';
position: absolute;
left: 0;
top: 0;
height: 100%;
width :100%;
background-color: green;
z-index: -1;
}

.quiz-box .opcoes .opcao.correta{
	color: #ffffff;
}

@keyframes fadeIn {
	0%{
		opacity: 0;
	}
	100%{
		opacity: 1;
	}
}


.quiz-box .btn{
	margin: 10px 0;
	cursor: pointer;
}


.quiz-box .indicador-resposta div{
	height: 40px;
	width: 40px;
	display: inline-block;
	background-color: #cccccc;
	border-radius: 50%;
	margin-top: 15px;
}

.quiz-box .indicador-resposta{
	border-top: 1px solid #cccccc;}

.quiz-box .indicador-resposta div.correta {
	background-color: green;
	background-repeat: no-repeat;
}
.quiz-box .indicador-resposta div.errada {
	background-color: red;
}

.result-box {
	text-align: center;
}

.result-box h1 {
	font-size: 36px;
	line-height: 42px;indicador-resposta
}
.result-box table {
	margin :30px 0;
	width: 100%;
	border-collapse: collapse;

}
.result-box table td {
	border:1px solid #cccccc;
	padding: 8px 15px;
	font-weight: 500;
	color: #000000
	font-size : 18px;
}

.result-box .hide{
	display: none;
}
</style>


</head>

<boby>

<div class ="home-box custom-box ">
	<h3>Bem vindo ao Quiz! <br>No nosso Quiz, você aprenderá sobre os Fatos e Fakes do CV-19</h3>
	<p>Total de questoes: <span class="total-questoes">10</span></p>
	<button type="button" class="btn" onclick="startQuiz()">Começar o Jogo</button>
</div>
<div class ="quiz-box custom-box hide "> 
<div class="numero-questao"></div>
 <div class="texto-quest"> </div>
 <div class="opcoes"> </div> 
 <div class="next-questao-btn">
  <button type ="button" class="btn" onclick="next()">Next</button>
 </div>
 <div class ="indicador-resposta"> </div>  
</div>

<div class ="result-box custom-box hide"> 
	<h1>Resultado do Quiz</h1>
 <TABLE>
 	<tr>
 		<td> Total de Questoes </td>
 		<td><span class="total-questoes"></span></td>
 	</tr>
 
 	<tr>
 	<td>Acertos</td>
 		<td><span class="total-acertos"></span></td>
 	</tr>
 	<tr>
 	<td> Erros </td>
 		<td><span class="total-erros"></span></td>
 	</tr>
 </TABLE>
<button type="button" class="btn" onclick="tentar()">Tentar Novamente</button>
<button type="button" class="btn" onclick="inicio()">Inicio</button>
 </div>



<script type="text/javascript">
	//matriz dos objetos
const quiz =[
{
	q: 'Não preciso me preocupar em higienizar as compras do mercado, afinal, eu mesmo peguei da prateleira com as mãos limpas.Correto?',
	opcoes:['Fato','Fake'],
	resposta:1
},
{
	q: 'Os sintomas mais comuns da COVID-19 são: febre, tosse seca e cansaço.Correto?',
	opcoes:['Fato','Fake'],
	resposta:0
},

{
	q: 'Se me sinto bem e tomo todos os cuidados, não tem problema abraçar e beijar as pessoas que amo.Correto?',
	opcoes:['Fato','Fake'],
	resposta:1
},

{
	q: 'É possível estar com a COVID-19 por até 14 dias antes de apresentar os sintomas?',
	opcoes:['Fato','Fake'],
	resposta:0
},

{
	q: 'Fazer gargarejo com água morna, sal e vinagre previne infecção?',
	opcoes:['Fato','Fake'],
	resposta:1
},

{
	q: 'Gatos também podem ser infectdados?',
	opcoes:['Fato','Fake'],
	resposta:0
},

{
	q: 'Usando mascara é possível ficar infectado?',
	opcoes:['Fato','Fake'],
	resposta:1
},

{
	q: 'A COVID-19 é mais perigosa para indivíduos acima dos 60 anos ou debilitados, portadores de doenças crônicas e crianças?',
	opcoes:['Fato','Fake'],
	resposta:0
},
{
	q: 'O novo coronavírus não afeta crianças.?',
	opcoes:['Fato','Fake'],
	resposta:1
},
{
	q: 'A vacina da gripe não protege contra a COVID-19.?',
	opcoes:['Fato','Fake'],
    resposta:0
}
] 
const numeroquestao = document.querySelector(".numero-questao");
const textoquestao = document.querySelector(".texto-quest");
const opcoes = document.querySelector(".opcoes");
const containdicadores = document.querySelector (".indicador-resposta");
const homebox = document.querySelector (".home-box");
const quizbox = document.querySelector (".quiz-box");
const resultbox = document.querySelector (".result-box");



let contarquestao =0;
let questaoatual;
let avaliarquestao =[];
let avaliaropcoes =[];
let acertos = 0;
let erros = 0;
let tentativas = 0;


// coloca a questao dentro da matriz

function setAvaliarQuestao () {

	const totalquestoes = quiz.length;
	for (let i=0; 
		i<totalquestoes;
		 i++){
		//console.log(quiz[i])
		avaliarquestao.push(quiz[i])
	}
}
 //define o numero da questão e opçao
function getNovaQuestao() {
	numeroquestao.innerHTML = "Questão " + (contarquestao + 1) + " de " + quiz.length;
	//perguntas aleatorias

const questoesIndex = avaliarquestao [Math.floor(Math.random()  * avaliarquestao.length)]
questaoatual = questoesIndex;
textoquestao.innerHTML = questaoatual.q;


const indice1=avaliarquestao.indexOf(questoesIndex);
//evita que as questões se repitam
avaliarquestao.splice(indice1,1);

//console.log(questoesIndex)
//console.log(indice1)
//console.log (avaliarquestao)

//opçoes e comprimento da opçoes

const opcaoLen = questaoatual.opcoes.length
for (let i=0; i<opcaoLen; i++){
	avaliaropcoes.push(i)
}


 opcoes.innerHTML = ''; //evita que as  se repitam
  let animationDelay = 0.15;


for (let i=0; i<opcaoLen; i++){
	const opcaoIndex = avaliaropcoes [Math.floor(Math.random() * avaliaropcoes.length)];
	const indice2 = avaliaropcoes.indexOf(opcaoIndex);
	avaliaropcoes.splice(indice2,1);

	const opcao = document.createElement("div");
	opcao.innerHTML = questaoatual.opcoes[opcaoIndex];
	opcao.id = opcaoIndex;
	opcao.style.animationDelay = animationDelay + 's';
	animationDelay = animationDelay + 0.15;
	opcao.className = "opcao";
	opcoes.appendChild(opcao);
	opcao.setAttribute ("onclick","getResult(this)");

//console.log (questaoatual.opcoes)
//console.log(opcaoIndex)
}
//criar opçoes

contarquestao++

}

function getResult (element){
	const id = parseInt(element.id);
	
	if (id === questaoatual.resposta) {
		element.classList.add("correta");

		updateindicadorResposta ("correta");
		acertos++;
		console.log("correta : " + acertos)
		
	}
	else {
		element.classList.add("errada");
		updateindicadorResposta ("errada");

	 erros++;}
 //console.log("errada : " + erros)

}

function  indicadorResposta (){
	containdicadores.innerHTML = '';
	const totalquestoes = quiz.length;
	for (let i=0; i<totalquestoes; i++){
		const indicador = document.createElement ("div");
		containdicadores.appendChild(indicador);
	}
}

function updateindicadorResposta (marcarTipo){
	containdicadores.children[contarquestao -1].classList.add(marcarTipo)
}
function next(){
	if (contarquestao === quiz.length){
		console.log("Fim de jogo");
		fimdeJogo();
		
	}
	else 
		{getNovaQuestao();
		}
}

function fimdeJogo(){
	quizbox.classList.add("hide");

	resultbox.classList.remove("hide");
    
    resultadoQuiz ();

}

function resultadoQuiz (){ 
resultbox.querySelector(".total-questoes").innerHTML = contarquestao ;
resultbox.querySelector(".total-acertos").innerHTML =  acertos;
resultbox.querySelector(".total-erros").innerHTML = contarquestao - acertos;
}


function finalizaQuiz (){

 contarquestao =0;
 acertos = 0;
 erros = 0;

}

function tentar (){
	resultbox.classList.add("hide");

	quizbox.classList.remove("hide");

	finalizaQuiz ();
	startQuiz ();
}

function inicio(){
	resultbox.classList.add("hide");


	homebox.classList.remove("hide");
   finalizaQuiz ();


}


//inicia o jogo
 function startQuiz(){	
       homebox.classList.add("hide");

       quizbox.classList.remove("hide");

 //o primeiro define todas as questoes na matriz disponivel
     setAvaliarQuestao ();
    //o segundo chama a funcao getNovaQuestao
     getNovaQuestao ();
  //vai criar os indicadores das respostas
    indicadorResposta ();

}

</script>


</boby>
</html>
