# Desafio: Fundamentos Node.js


## 🚀 Sobre o desafio
Nesse desafio, você deve criar uma aplicação para continuar treinando o que você aprendeu até agora no Node.js junto ao TypeScript, utilizando o conceito de models, repositories e services!

Essa será uma aplicação para armazenar transações financeiras de entrada e saída, que deve permitir o cadastro e a listagem dessas transações.

## Rotas da aplicação
Agora que você já está com o template clonado, e pronto para continuar, você deve verificar os arquivos da pasta src e completar onde não possui código com o código para atingir os objetivos de cada rota.

<strong><code>POST /transactions:</code></strong> A rota deve receber title, value e type dentro do corpo da requisição, sendo type o tipo da transação, que deve ser income para entradas (depósitos) e outcome para saídas (retiradas). Ao cadastrar uma nova transação, ela deve ser armazenada dentro de um objeto com o seguinte formato :
<div class="highlight highlight-source-json"><pre>{
  <span class="pl-s"><span class="pl-pds">"</span>id<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>uuid<span class="pl-pds">"</span></span>,
  <span class="pl-s"><span class="pl-pds">"</span>title<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>Salário<span class="pl-pds">"</span></span>,
  <span class="pl-s"><span class="pl-pds">"</span>value<span class="pl-pds">"</span></span>: <span class="pl-c1">3000</span>,
  <span class="pl-s"><span class="pl-pds">"</span>type<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>income<span class="pl-pds">"</span></span>
}</pre></div>
<strong><code>GET /transactions:</code></strong> Essa rota deve retornar uma listagem com todas as transações que você cadastrou até agora, junto com o valor de soma de entradas, retiradas e total de crédito. Essa rota deve retornar um objeto com o formato a seguir:
<div class="highlight highlight-source-json"><pre>{
  <span class="pl-s"><span class="pl-pds">"</span>transactions<span class="pl-pds">"</span></span>: [
    {
      <span class="pl-s"><span class="pl-pds">"</span>id<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>uuid<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>title<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>Salário<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>value<span class="pl-pds">"</span></span>: <span class="pl-c1">4000</span>,
      <span class="pl-s"><span class="pl-pds">"</span>type<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>income<span class="pl-pds">"</span></span>
    },
    {
      <span class="pl-s"><span class="pl-pds">"</span>id<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>uuid<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>title<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>Freela<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>value<span class="pl-pds">"</span></span>: <span class="pl-c1">2000</span>,
      <span class="pl-s"><span class="pl-pds">"</span>type<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>income<span class="pl-pds">"</span></span>
    },
    {
      <span class="pl-s"><span class="pl-pds">"</span>id<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>uuid<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>title<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>Pagamento da fatura<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>value<span class="pl-pds">"</span></span>: <span class="pl-c1">4000</span>,
      <span class="pl-s"><span class="pl-pds">"</span>type<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>outcome<span class="pl-pds">"</span></span>
    },
    {
      <span class="pl-s"><span class="pl-pds">"</span>id<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>uuid<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>title<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>Cadeira Gamer<span class="pl-pds">"</span></span>,
      <span class="pl-s"><span class="pl-pds">"</span>value<span class="pl-pds">"</span></span>: <span class="pl-c1">1200</span>,
      <span class="pl-s"><span class="pl-pds">"</span>type<span class="pl-pds">"</span></span>: <span class="pl-s"><span class="pl-pds">"</span>outcome<span class="pl-pds">"</span></span>
    }
  ],
  <span class="pl-s"><span class="pl-pds">"</span>balance<span class="pl-pds">"</span></span>: {
    <span class="pl-s"><span class="pl-pds">"</span>income<span class="pl-pds">"</span></span>: <span class="pl-c1">6000</span>,
    <span class="pl-s"><span class="pl-pds">"</span>outcome<span class="pl-pds">"</span></span>: <span class="pl-c1">5200</span>,
    <span class="pl-s"><span class="pl-pds">"</span>total<span class="pl-pds">"</span></span>: <span class="pl-c1">800</span>
  }
}</pre></div>

<strong>Dica 1:</strong> Dentro de balance, o income é a soma de todos os valores das transações com type income. O outcome é a soma de todos os valores das transações com type outcome, e o total é o valor de income - outcome.

<strong>Dica 2:</strong> Para fazer a soma dos valores, você pode usar a função reduce para agrupar as transações pela propriedade type, assim você irá conseguir somar todos os valores com facilidade e obter o retorno do balance.

## Especificação dos testes
Em cada teste, tem uma breve descrição no que sua aplicação deve cumprir para que o teste passe.

Caso você tenha dúvidas quanto ao que são os testes, e como interpretá-los, dé uma olhada em nosso FAQ.

<strong>Para esse desafio temos os seguintes testes:</strong>

<strong><code>should be able to create a new transaction:</code></strong> Para que esse teste passe, sua aplicação deve permitir que uma transação seja criada, e retorne um json com a transação criada.

<strong><code>should be able to list the transactions:</code></strong> Para que esse teste passe, sua aplicação deve permitir que seja retornado um objeto contendo todas as transações junto ao balanço de income, outcome e total das transações que foram criadas até o momento.

<strong><code>should not be able to create outcome transaction without a valid balance:</code></strong> Para que esse teste passe, sua aplicação não deve permitir que uma transação do tipo outcome extrapole o valor total que o usuário tem em caixa, retornando uma resposta com código HTTP 400 e uma mensagem de erro no seguinte formato: { error: string }
