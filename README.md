# Sistema de Adoção de Pets

## Descrição do Projeto

Este projeto consiste em um sistema de adoção de pets desenvolvido em Python para a disciplina de Tecnologia de Orientação a Objetos. O objetivo é aplicar os principais conceitos da Programação Orientada a Objetos, como abstração, encapsulamento, herança e polimorfismo, além de utilizar padrões de projeto para organizar melhor a estrutura do sistema.

O sistema permite cadastrar animais, cadastrar adotantes, criar solicitações de adoção, aprovar ou rejeitar solicitações e listar os dados cadastrados.

## Diagrama de Classes UML

<img width="1536" height="1024" alt="diagramaUML" src="https://github.com/user-attachments/assets/7fb503f7-6ab4-4fe8-98a6-65fa7f99249a" />

## Funcionalidades Implementadas

* Cadastro de cachorros;
* Cadastro de gatos;
* Cadastro de adotantes;
* Listagem de animais cadastrados;
* Criação de solicitações de adoção;
* Aprovação de solicitações;
* Rejeição de solicitações;
* Listagem de solicitações;
* Alteração do status do animal ao ser adotado.

## Classes do Sistema

### Animal

Classe abstrata que representa um animal genérico no sistema. Possui atributos comuns a todos os animais, como id, nome, idade, sexo e status.

### Cachorro

Classe que herda de `Animal` e representa um cachorro. Possui o atributo específico raça e implementa o método `exibir_dados`.

### Gato

Classe que herda de `Animal` e representa um gato. Possui o atributo específico pelagem e implementa o método `exibir_dados`.

### Adotante

Representa uma pessoa interessada em adotar um animal. Armazena nome, CPF e telefone.

### SolicitacaoAdocao

Representa o pedido de adoção de um animal por um adotante. Utiliza o padrão State para controlar o estado da solicitação.

### EstadoSolicitacao

Classe abstrata que define os métodos que todos os estados da solicitação devem implementar: `aprovar` e `rejeitar`.

### EstadoPendente, EstadoAprovada e EstadoRejeitada

Classes concretas que representam os possíveis estados de uma solicitação de adoção.

### AnimalFactory

Classe responsável por aplicar o Factory Pattern, centralizando a criação de objetos do tipo `Cachorro` e `Gato`.

### Abrigo

Classe responsável por gerenciar os animais e as solicitações do sistema. Implementa o Singleton Pattern para garantir que exista apenas uma instância do abrigo durante a execução.

## Pilares da Programação Orientada a Objetos

### Abstração

A abstração aparece na classe `Animal`, que representa um conceito genérico de animal, e na classe `EstadoSolicitacao`, que representa um estado genérico de solicitação.

### Encapsulamento

O encapsulamento foi aplicado com atributos privados, como `__nome`, `__idade`, `__status`, `__animais` e `__solicitacoes`, acessados por métodos e propriedades.

### Herança

A herança aparece nas classes `Cachorro` e `Gato`, que herdam de `Animal`, e nas classes de estado, que herdam de `EstadoSolicitacao`.

### Polimorfismo

O polimorfismo aparece no método `exibir_dados`, implementado de formas diferentes em `Cachorro` e `Gato`, e nos métodos `aprovar` e `rejeitar`, implementados de formas diferentes em cada estado da solicitação.

## Padrões de Projeto Utilizados

### Factory Pattern

O Factory Pattern foi aplicado na classe `AnimalFactory`, responsável por criar objetos do tipo `Cachorro` ou `Gato` de acordo com o tipo informado.

### State Pattern

O State Pattern foi aplicado no controle das solicitações de adoção. Cada estado da solicitação possui sua própria classe e define como deve se comportar ao aprovar ou rejeitar uma solicitação.

### Singleton Pattern

O Singleton Pattern foi aplicado na classe `Abrigo`, garantindo que exista apenas uma instância do abrigo durante toda a execução do sistema.

## Como Executar o Projeto

1. Faça o download ou clone este repositório.
2. Abra a pasta do projeto no **Visual Studio Code**.
3. Certifique-se de que a extensão **Python** esteja instalada no VS Code.
4. Abra o arquivo `main.py`.
5. Clique no botão **Run Python File** no canto superior direito do VS Code ou execute o arquivo pelo terminal integrado utilizando:

```bash
python main.py
```

6. O menu do sistema será exibido no terminal, permitindo cadastrar animais, adotantes e gerenciar as solicitações de adoção.

## Testes do Sistema

Os testes podem ser realizados diretamente pelo menu do sistema, executando ações como:

1. Cadastrar um cachorro;
2. Cadastrar um gato;
3. Cadastrar um adotante;
4. Criar uma solicitação de adoção;
5. Aprovar ou rejeitar a solicitação;
6. Listar animais e solicitações para verificar as alterações.

## Detalhamento de Aprendizado

Durante o desenvolvimento deste projeto, foi possível compreender melhor como estruturar um sistema utilizando Orientação a Objetos. O projeto ajudou a praticar a separação de responsabilidades entre classes, o uso de herança, classes abstratas, encapsulamento e padrões de projeto.

### Dificuldades Encontradas

Uma das principais dificuldades foi compreender como aplicar padrões de projeto de forma coerente dentro do sistema, principalmente o State Pattern, pois ele exige separar os comportamentos de acordo com o estado atual da solicitação.

### Como resolvi

A solução foi dividir a solicitação em estados diferentes, criando uma classe abstrata para representar o estado geral e classes concretas para os estados pendente, aprovada e rejeitada. Também foi utilizado o Factory Pattern para centralizar a criação dos animais e o Singleton Pattern para controlar a instância única do abrigo.

### Principal Aprendizado

O principal aprendizado foi entender que a Orientação a Objetos não se resume apenas à criação de classes, mas também envolve organizar responsabilidades, reduzir repetição de código e criar uma estrutura mais fácil de manter e expandir.

## Declaração de Uso de IA

Utilizei IA como ferramenta de apoio.

Ferramenta(s): ChatGPT.

Finalidade: Apoio na organização da estrutura do projeto, explicação dos conceitos de Orientação a Objetos, revisão da aplicação dos padrões de projeto e auxílio na documentação.

Validação: Declaro que todo o código gerado foi lido, testado e ajustado conforme as necessidades específicas do projeto e da disciplina. A responsabilidade pela arquitetura, decisões de design e correção do código é de minha total responsabilidade.
