# Introdução ao Flutter e Criação de uma Aplicação Simples

## Abertura (1 minuto)

### Introdução do Apresentador

 Olá, pessoal! Bem-vindos ao nosso canal. Hoje vamos explorar o mundo do Flutter, uma ferramenta incrível para criar aplicativos móveis rápidos e bonitos.

### Objetivo do Vídeo

 Neste vídeo, vamos configurar seu ambiente de desenvolvimento Flutter, revisar os fundamentos do Dart e construir uma aplicação simples juntos. Vamos lá?

---

## Parte 1: Introdução ao Flutter (2 minutos)

### O que é Flutter?

 O Flutter é um kit de desenvolvimento de aplicativos móveis criado pelo Google. Ele oferece uma maneira rápida de criar aplicativos lindos para iOS e Android a partir de um único código.

### Configurando o Ambiente

1. **Instalação do SDK do Flutter**
   - Mostre rapidamente como baixar e instalar o Flutter SDK do site oficial.
   > Certifique-se de adicionar o Flutter ao seu PATH.

2. **Configuração de um Editor de Código**
   > Hoje vamos usar o Visual Studio Code. Instalem a extensão do Flutter para facilitar o desenvolvimento.

3. **Configuração de um Emulador**
   - Demonstre como configurar um emulador Android através do Android Studio.

---

## Parte 2: Fundamentos do Dart (3 minutos)

### Introdução à Linguagem Dart

 Dart é a linguagem de programação que utilizamos com Flutter. Ele é fácil de aprender e perfeito para nosso propósito.

### Variáveis e Tipos de Dados

- Exemplo:

  ```dart
  int idade = 30; 
  String nome = 'João';
  ```

### Controle de Fluxo (if e loops)

 Vamos ver um exemplo rápido de controle de fluxo usando uma condição if.

- Exemplo:

  ```dart
  if (idade > 18) {
    print('Você é maior de idade.');
  }
  ```

### Funções e Métodos

 Veja como criar uma função simples.

- Exemplo:

  ```dart
  void saudacao() {
    print('Olá, bem-vindo ao nosso App!');
  }
  saudacao();
  ```

### Classes e Objetos

 Vamos dar uma olhada em como criar uma classe.

- Exemplo:

  ```dart
  class Pessoa {
    String nome;
    int idade;

    Pessoa(this.nome, this.idade);

    void mostrar() {
      print('Nome: $nome, Idade: $idade');
    }
  }
  ```

---

## Parte 3: Widgets no Flutter (5 minutos)

### O Que São Widgets?

 No Flutter, tudo é um widget. Vamos começar com dois tipos básicos: Stateless e Stateful.

### Layouts em Flutter

 Vamos criar um layout utilizando o Row e o Column.

- Exemplo:

  ```dart
  Column(
    children: [
      Text('Bem-vindo'),
      Row(
        children: [
          Text('Flutter'),
          Text('é incrível!'),
        ],
      ),
    ],
  );
  ```

### Navegação entre Telas

 Agora, vamos adicionar navegação de uma tela para outra usando o Navigator.

- Código Exemplo:

  ```dart
  Navigator.push(
    context,
    MaterialPageRoute(builder: (context) => SegundaTela()),
  );
  ```

### Formulários e Validação

 Vamos configurar um formulário simples.

- Exemplo:

  ```dart
  final _formKey = GlobalKey<FormState>();
  Form(
    key: _formKey,
    child: Column(
      children: [
        TextFormField(
          decoration: InputDecoration(labelText: 'Nome'),
          validator: (value) {
            if (value == null || value.isEmpty) {
              return 'Por favor, insira seu nome';
            }
            return null;
          },
        ),
      ],
    ),
  );
  ```

---

## Parte 4: Construindo uma Aplicação Simples (6 minutos)

### Iniciando o Projeto

 Vamos criar nosso projeto com o comando:

```bash
flutter create app_exemplo
```

 No Visual Studio Code, vamos abrir o arquivo `lib/main.dart`.

### Estrutura do Projeto

 Vamos explicar rapidamente a estrutura básica do Flutter, mencionando `main.dart` e `pubspec.yaml`.

### Aplicação: Contador Simples

 Agora, criaremos um contador simples no Flutter.

- Código Completo:

  ```dart
  import 'package:flutter/material.dart';

  void main() {
    runApp(MeuApp());
  }

  class MeuApp extends StatelessWidget {
    @override
    Widget build(BuildContext context) {
      return MaterialApp(
        home: Contador(),
      );
    }
  }

  class Contador extends StatefulWidget {
    @override
    _ContadorState createState() => _ContadorState();
  }

  class _ContadorState extends State<Contador> {
    int _contagem = 0;

    void _incrementarContador() {
      setState(() {
        _contagem++;
      });
    }

    @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(
          title: Text('Contador Simples'),
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              Text(
                'Você pressionou o botão este número de vezes:',
              ),
              Text(
                '$_contagem',
                style: Theme.of(context).textTheme.headline4,
              ),
            ],
          ),
        ),
        floatingActionButton: FloatingActionButton(
          onPressed: _incrementarContador,
          tooltip: 'Incrementar',
          child: Icon(Icons.add),
        ),
      );
    }
  }
  ```

- Execute a aplicação e mostre sua funcionalidade.

---

## Parte 5: Integração com APIs (2 minutos)

### Consumindo uma API REST

 Vamos fazer uma requisição simples usando o pacote http.

- Dê um exemplo rápido de requisição GET.

### Exibição dos Dados

 Veja como podemos exibir dados em um ListView.

---

## Conclusão (1 minuto)

### Resumo dos Tópicos

 Hoje revisamos o Flutter e Dart, construímos um aplicativo simples e vimos como integrar APIs.

### Chamada para Ação

 Se você gostou deste vídeo, inscreva-se no canal e ative o sininho para mais conteúdo!

### Agradecimentos

 Obrigado por assistir e até a próxima!
