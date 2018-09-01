# Desafio da semana #3

```js
// Declarar uma variável qualquer, que receba um objeto vazio.
var obj = {};

/*
Declarar uma variável `pessoa`, que receba suas informações pessoais.
As propriedades e tipos de valores para cada propriedade desse objeto devem ser:
- `nome` - String
- `sobrenome` - String
- `sexo` - String
- `idade` - Number
- `altura` - Number
- `peso` - Number
- `andando` - Boolean - recebe "falso" por padrão
- `caminhouQuantosMetros` - Number - recebe "zero" por padrão
*/
var Pessoa = {
  nome: 'Lucas',
  sobrenome: 'Augusto',
  sexo: 'Masculino',
  idade: 25,
  altura: 1.76,
  peso: 96,
  andando: false,
  caminhouQuantosMetros: 0
}

/*
Adicione um método ao objeto `pessoa` chamado `fazerAniversario`. O método deve
alterar o valor da propriedade `idade` dessa pessoa, somando `1` a cada vez que
for chamado.
*/
Pessoa.fazerAniversario = function () {
  Pessoa.idade += 1;
}

/*
Adicione um método ao objeto `pessoa` chamado `andar`, que terá as seguintes
características:
- Esse método deve receber por parâmetro um valor que representará a quantidade
de metros caminhados;
- Ele deve alterar o valor da propriedade `caminhouQuantosMetros`, somando ao
valor dessa propriedade a quantidade passada por parâmetro;
- Ele deverá modificar o valor da propriedade `andando` para o valor
booleano que representa "verdadeiro";
*/
Pessoa.andar = function (passos) {
  Pessoa.andando = true;
  Pessoa.caminhouQuantosMetros += passos;
  return Pessoa.andando;
}

/*
Adicione um método ao objeto `pessoa` chamado `parar`, que irá modificar o valor
da propriedade `andando` para o valor booleano que representa "falso".
*/
Pessoa.parar = function () {
  Pessoa.andando = false;
  return Pessoa.andando;
}

/*
Crie um método chamado `nomeCompleto`, que retorne a frase:
- "Olá! Meu nome é [NOME] [SOBRENOME]!"
*/
Pessoa.nomeCompleto = function () {
  return Pessoa.nome + ' ' + Pessoa.sobrenome;
}

/*
Crie um método chamado `mostrarIdade`, que retorne a frase:
- "Olá, eu tenho [IDADE] anos!"
*/
Pessoa.mostrarIdade = function () {
  return 'Olá, eu tenho ' + Pessoa.idade + ' anos!';
}

/*
Crie um método chamado `mostrarPeso`, que retorne a frase:
- "Eu peso [PESO]Kg."
*/
Pessoa.mostrarPeso = function () {
  return 'Eu tenho ' + Pessoa.peso + 'Kg';
}

/*
Crie um método chamado `mostrarAltura` que retorne a frase:
- "Minha altura é [ALTURA]m."
*/
Pessoa.mostrarAltura = function () {
  return 'Minha altura é ' + Pessoa.altura;
}

/*
Agora vamos brincar um pouco com o objeto criado:
Qual o nome completo da pessoa? (Use a instrução para responder e comentários
inline ao lado da instrução para mostrar qual foi a resposta retornada)
*/
Pessoa.nomeCompleto; // Lucas Augusto

/*
Qual a idade da pessoa? (Use a instrução para responder e comentários
inline ao lado da instrução para mostrar qual foi a resposta retornada)
*/
Pessoa.mostrarIdade; // Olá, eu tenho 25 anos!

/*
Qual o peso da pessoa? (Use a instrução para responder e comentários
inline ao lado da instrução para mostrar qual foi a resposta retornada)
*/
Pessoa.mostrarPeso; // Eu tenho 96Kg

/*
Qual a altura da pessoa? (Use a instrução para responder e comentários
inline ao lado da instrução para mostrar qual foi a resposta retornada)
*/
Pessoa.mostrarAltura; // Minha altura é 1.76

/*
Faça a `pessoa` fazer 3 aniversários.
*/
Pessoa.fazerAniversario();
Pessoa.fazerAniversario();
Pessoa.fazerAniversario();

/*
Quantos anos a `pessoa` tem agora? (Use a instrução para responder e
comentários inline ao lado da instrução para mostrar qual foi a resposta
retornada)
*/
Pessoa.mostrarIdade; // Olá, eu tenho 28 anos!

/*
Agora, faça a `pessoa` caminhar alguns metros, invocando o método `andar` 3x,
com metragens diferentes passadas por parâmetro.
*/
Pessoa.andar(100);
Pessoa.andar(250);
Pessoa.andar(500);

/*
A pessoa ainda está andando? (Use a instrução para responder e comentários
inline ao lado da instrução para mostrar qual foi a resposta retornada)
*/
Pessoa.andando; // true

/*
Se a pessoa ainda está andando, faça-a parar.
*/
Pessoa.parar();

/*
E agora: a pessoa ainda está andando? (Use uma instrução para responder e
comentários inline ao lado da instrução para mostrar a resposta retornada)
*/
Pessoa.andando; // false

/*
Quantos metros a pessoa andou? (Use uma instrução para responder e comentários
inline ao lado da instrução para mostrar a resposta retornada)
*/
Pessoa.caminhouQuantosMetros; // 750

/*
Agora vamos deixar a brincadeira um pouco mais divertida! :D
Crie um método para o objeto `pessoa` chamado `apresentacao`. Esse método deve
retornar a string:
- "Olá, eu sou o [NOME COMPLETO], tenho [IDADE] anos, [ALTURA], meu peso é [PESO] e, só hoje, eu já caminhei [CAMINHOU QUANTOS METROS] metros!"

Só que, antes de retornar a string, você vai fazer algumas validações:
- Se o `sexo` de `pessoa` for "Feminino", a frase acima, no início da
apresentação, onde diz "eu sou o", deve mostrar "a" no lugar do "o";
- Se a idade for `1`, a frase acima, na parte que fala da idade, vai mostrar a
palavra "ano" ao invés de "anos", pois é singular;
- Se a quantidade de metros caminhados for igual a `1`, então a palavra que
deve conter no retorno da frase acima é "metro" no lugar de "metros".
- Para cada validação, você irá declarar uma variável localmente (dentro do
método), que será concatenada com a frase de retorno, mostrando a resposta
correta, de acordo com os dados inseridos no objeto.
*/
Pessoa.apresentacao = function () {
  var sexo = (Pessoa.sexo === 'Masculino') ? 'o ' : 'a ';
  var anos = (Pessoa.idade === 1) ? ' ano, ' : ' anos, ' ;
  var metrosCaminhados = (Pessoa.caminhouQuantosMetros === 1) ? ' metro!' : ' metros!';

  return 'Olá, eu sou ' + sexo + Pessoa.nomeCompleto() + ', tenho ' + Pessoa.idade + anos + 'meu peso é ' + Pessoa.peso + 'Kg e, só hoje, eu já caminhei ' + Pessoa.caminhouQuantosMetros + metrosCaminhados;
}

// Agora, apresente-se ;)
Pessoa.apresentacao();
```
