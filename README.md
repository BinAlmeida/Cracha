# MeuCrachaApp

Aplicativo desenvolvido em Flutter e Dart para criação de um crachá digital estudantil. O projeto foi desenvolvido de forma incremental, com uma versão base e 8 exercícios de fixação, onde cada etapa adicionou uma nova funcionalidade ou alteração na estrutura da aplicação.

## Versão Base — V.0.0

A versão inicial apresentava um único crachá estudantil na tela, contendo as informações do aluno, como nome, curso, RA e e-mail, além de ícones e uma imagem representando o perfil.
A interface foi construída principalmente com `Scaffold`, `AppBar`, `Container`, `Column`, `Row`, `Card`, `CircleAvatar`, `Icon` e `Text`.
O crachá era montado diretamente no `main.dart`, sem um widget separado para reutilização.

---

## Exercício 01 — V.0.0.1

**Objetivo:** alterar as cores principais do crachá.

### O que mudou

O `Container` principal passou a utilizar:
```dart
color: Colors.green.shade50,

Os ícones que anteriormente utilizavam a cor definida na versão base passaram a utilizar:
color: Colors.green,

### Resultado
O crachá passou a ter um fundo verde-claro e seus ícones passaram a utilizar verde como cor principal.

---

## Exercício 02 — V.0.0.2

Objetivo: informar a situação da matrícula do estudante.

### O que mudou

Foi adicionada uma nova Row abaixo do e-mail contendo:
Icons.check_circle
e o texto:
Status: Matriculado / Ativo

O novo campo manteve o mesmo padrão visual dos demais dados do crachá, utilizando o ícone na cor verde.

###Resultado
Além dos dados pessoais e acadêmicos, o crachá passou a informar que o estudante está matriculado e ativo.

---

## Exercício 03 — V.0.0.3

Objetivo: substituir o ícone genérico do perfil por uma imagem real.

### O que mudou

O CircleAvatar deixou de utilizar somente um ícone e passou a utilizar uma imagem da internet através de:
foregroundImage: NetworkImage(...)

Foi utilizada uma imagem hospedada externamente para representar a foto de perfil.

## Resultado
O círculo de perfil passou a exibir uma imagem real carregada pela internet.

---

## Exercício 04 — V.0.0.4

Objetivo: provocar um erro proposital no código para observar a mensagem apresentada pelo compilador.

### O que mudou

A propriedade:
child:
do Container foi propositalmente substituída por:
children:
e foi passada uma lista de widgets.

## Resultado

O código passou a apresentar erro de compilação, pois Container possui a propriedade child, que recebe apenas um widget, e não a propriedade children, utilizada para listas de widgets.
O exercício serviu para identificar e compreender erros de tipagem e propriedades dos widgets Flutter.

---

## Exercício 05 — V.0.0.5

Objetivo: adicionar um espaçamento interno extra no conteúdo do crachá.

### O que mudou

A Column que continha os elementos do cartão foi envolvida por um Padding:
Padding(
  padding: const EdgeInsets.all(8),
  child: Column(
    ...
  ),
)

## Resultado
Foi adicionado um espaçamento interno de 8 pixels em todos os lados entre a borda do cartão e seus elementos.

---

## Exercício 06 — V.0.0.6

Objetivo: adicionar um botão no final do crachá.

### O que mudou

Foi acrescentado um ElevatedButton após os dados do estudante:
ElevatedButton(
  onPressed: () {},
  child: const Text(
    'Validar Carteirinha',
  ),
)
O botão possui uma ação vazia em onPressed, conforme solicitado no exercício.

## Resultado
O crachá passou a ter um rodapé contendo o botão "Validar Carteirinha".

---

## Exercício 07 — V.0.0.7

Objetivo: separar a estrutura do crachá em um widget reutilizável.

### O que mudou
A estrutura do cartão foi extraída do main.dart e transformada em um novo widget chamado:
CartaoEstudante
O widget foi colocado no arquivo:
lib/widgets/cartao_estudante.dart
Também foi realizada a importação no main.dart:
import 'widgets/cartao_estudante.dart';
O widget passou a receber os dados do estudante por parâmetros:
nome
curso
ra
email
imagem
Todos esses parâmetros foram definidos como obrigatórios.

## Resultado
O código passou a ficar mais organizado e reutilizável, permitindo criar diferentes crachás utilizando o mesmo widget CartaoEstudante.

---

## Exercício 08 — V.0.0.8

Objetivo: criar uma lista com três crachás diferentes.

### O que mudou
Foi criado um novo arquivo:
lib/desafio_lista.dart
Nesse arquivo foi criada a tela DesafioLista.
A tela utiliza:
SingleChildScrollView
e uma:
Column
para apresentar três widgets CartaoEstudante, cada um representando um estudante diferente.
Foram adicionados os seguintes estudantes:
Ana Silva Santos
Carlos Oliveira
Mariana Souza
Cada crachá possui nome, curso, RA, e-mail e uma imagem própria.
Também foi adicionada uma navegação no main.dart para acessar essa nova tela através do botão:
Ver 3 Crachás
A navegação foi realizada utilizando:
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => const DesafioLista(),
  ),
);

## Resultado
A aplicação passou a possuir duas telas:
A tela principal com o crachá individual.
A tela Lista de Estudantes, contendo três crachás diferentes um abaixo do outro.

---

### Histórico das versões
Versão	Exercício	Alteração principal
V.0.0	Base	Criação do crachá estudantil
V.0.0.1	Exercício 01	Fundo verde-claro e ícones verdes
V.0.0.2	Exercício 02	Status da matrícula
V.0.0.3	Exercício 03	Imagem de perfil via NetworkImage
V.0.0.4	Exercício 04	Erro proposital com children
V.0.0.5	Exercício 05	Padding de 8 pixels
V.0.0.6	Exercício 06	Botão "Validar Carteirinha"
V.0.0.7	Exercício 07	Criação do widget CartaoEstudante
V.0.0.8	Exercício 08	Lista com três crachás

---

###Tecnologias utilizadas
Flutter
Dart
Git
GitHub
