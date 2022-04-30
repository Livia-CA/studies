# Boas Práticas :books: :fire:



## BEM (Block Element Modifier)

*Melhorando sua organização no CSS*

* Metodologia para ajudar o desenvolvedor a criar componentes reutilizáveis e facilmente compartilháveis dentro do frontend;
*  Simples de ser implementado, pois basta seguir a convenção de nomes;
*  Possível criar blocos modularizados dentro do seu código fonte;
*  Pode ser utilizado com outros padrões e metodologias de organização;
* Mais exemplos em http://getbem.com/

---

### Block

Entidade autônoma que é significativa por si só.

##### Exemplos

`header`, `container`, `menu`, `checkbox`,`input`



### Element

Uma parte de um bloco que não tem significado autônomo e está semanticamente vinculada ao seu bloco.

##### Exemplos

`menu item`, `list item`, `checkbox caption`,`header`,`title`



### Modifier

Uma bandeira em um bloco ou elemento. Use-os para mudar a aparência ou o comportamento.

##### Exemplos

`disabled`, `highlighted`, `checked`, `fixed`, `size big`,`color: yellow`

---

### Block__Element--Modifier

* Padronização para classes de elementos utilizamos 2x '__' (underline)

  - Ex: .list__ item, .list__title

* Para classes de modificadores utilizamos 2x '--' (traços)

  - Ex: .list__ item--highlight, .list__author--active

* Para blocos não é necessário, porque ele é uma classe única que vai envolver todos os outros elementos no HTML

  

## Design System

*Padronizando a identidade do seu produto*

* Documento vivo de design com todos os componentes de um software;

* Tem por objetivo aumentar a eficiência dos designers no momento de especificação;

* Trás consistencia para os usuarios (inclusive desenvolvedores) com uma linguagem clara e unificada;

*  Deve ter um objetivo claro no momento de sua criação;

*  Não é obrigatório, mas extremamente recomendável que tenham referências de implementação.

  

## Storybook

*Contando historinhas sobre seu frontend*

* Ferramenta para preparar o ambiente de desenvolvimento de componentes de Ul;

* Permite desenvolver de forma isolada componentes de interfaces;

* Integrado os principais frameworks frontend utilizados (VueJS, Angular, React);

* Possibilidade de trabalhar com addons, adicionando mais funcionalidades;

* Exibe na interface erros de sintaxe.

* https://storybook.js.org/

  

## Micro Frontend

* Evolução natural no desenho de arquitetura de software;
* Aprofundamento em https://martinfowler.com/articles/micro-frontends.html;
* Crie provas de conceito https://single-spa.is.org/.



## MVC (Model View Controller)

* Padrão arquitetural que divide os elementos da nossa aplicação em três camadas

  * Modelo

    * Gerenciar as Entidades do nosso sistema
    * Lidar com informações da nossa aplicação
    * Receber, tratar e validar todos os dados
    * Conectar a base de dados

  * Visão

    * Camada de interação do usuário com o sistema

    * Renderiza componentes que fazem parte da experiencia da aplicação

  * Controlador

    * Recebe requisições e eventos do usuário, trata-las e responde-las

    * Requer ao Model os dados necessários

    * Encaminha resposta do Model para o View

    * Captura dados na View e encaminha para o Model

      

## MVVM (Model View ViewModel)

* Padrão arquitetural que divide os elementos da nossa aplicação em três camadas
  * Modelo
    * Regras de Negócio
    * Encapsula dados
    * Prover notificações através da interface (INotifyPropertyChanged)
  * Visão
    * Camada de interação do usuário com a aplicação
    * Renderiza componentes que fazem parte da experiência da aplicação
    * Define aparência e estrutura do que o usuário visualiza na tela
    * Normalmente contém um Code-Behind sobre a lógica dessa interface
    * Deve possuir um Binding Context indicando qual ViewModel está referenciada
  * ViewModel
    * Trata da Lógica de controles
    * Não conhece a View
    * Lança Notificações de estado ou de alterações (OnNotifyPropertyChanged)
      



## Design Patterns: Singleton, Strategy e Adapter

### Singleton

* Padrão de projeto do tipo CREATIONAL;
* Garante que existe apenas uma instância de uma classe;
* Provê acesso global por toda a aplicação em um único ponto.



### Strategy

* Padrão de projeto do tipo BEHAVIORAL
* Pode definir uma série de algoritmos diferentes cada um separado em suas devidas classes mas que pode ser intercambiáveis
* Vamos ao exemplo em: https://github.com/jcbombardelli/gama-nas-boas-praticas/tree/master/stategy



### Adapter

* Padrão de projeto do tipo STRUCTURAL
* Serve para 'adaptar' nossa implementação já existente a um novo cenário diferente daquele originalmente desenhado
* Ajuda muito quando precisamos utilizar integrações com serviços terceiros (WebService do governo por exemplo)
* Vamos ao exemplo em: https://github.com/jcbombardelli/gama-nas-boas-praticas/tree/master/adapter



***

#### Links para materiais complementares: 

*  Apostila
  * https://drive.google.com/file/d/1-dTqNpLFhpF0y2RboIhAB-9cIvimk4iI/view
*  Boas práticas no front-end, técnicas e estratégias
  * https://open.spotify.com/episode/4RhhCrkQlTx6MehkuODDMN
*  Design System na prática, por designers e desenvolvedores
  * http://eng.dito.com.br/design-system-na-pratica-por-designers-e-desenvolvedores
* Micro Front-end
  * https://medium.com/@danielfernandes/micro-front-end-a9d654a67528
*  Design Patterns // Dicionário do Programador 
  * https://www.youtube.com/watch?v=J-lHpiu-Twk