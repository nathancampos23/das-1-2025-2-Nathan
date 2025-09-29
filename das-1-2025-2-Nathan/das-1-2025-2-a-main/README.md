DESIGN E ARQUITETURA DE SOFTWARE I
📍 Abstração

Abstração é o processo de representar elementos do mundo real dentro de um sistema de software. Em Java, por exemplo, isso é frequentemente feito através de classes localizadas no pacote entity, que modelam entidades correspondentes aos dados armazenados no banco de dados.

📍 Princípios de Projeto de Código

Esses princípios são boas práticas que orientam a forma como o software deve ser desenvolvido. O objetivo é tornar o sistema mais simples de compreender, manter e evoluir. Conceitos como abstração, modularização, baixo acoplamento e alta coesão são fundamentais.

Organização típica por camadas:

Controller: responsável pela interface de entrada, como APIs REST ou páginas HTML.

Entity: representa os dados do sistema.

Repository: faz a comunicação com o banco de dados.

Service: contém a lógica de negócios.

Config: concentra as configurações do sistema.

📍 Padronização de Código

Trata-se de seguir regras e convenções para escrita do código, garantindo uniformidade entre diferentes desenvolvedores.
Essa padronização facilita a leitura e manutenção do projeto.
Por exemplo, em Java:

Classes seguem a convenção CamelCase (ex.: MinhaClasse).

Variáveis utilizam camelCase (ex.: minhaVariavel).

📍 Ocultamento de Informação (Encapsulamento)

Encapsular significa esconder os detalhes internos de uma classe, expondo apenas o que é necessário para outras partes do sistema.
Isso reduz dependências diretas e protege a implementação interna.
Em Java, é comum declarar os atributos como private e disponibilizar métodos de acesso (get e set).

📍 Coesão

Refere-se ao quão bem os elementos dentro de uma classe ou módulo trabalham juntos para cumprir uma única responsabilidade.
Alta coesão deixa o código mais claro, organizado e fácil de manter.

📍 Acoplamento

Mede o grau de dependência entre diferentes partes do sistema.
O ideal é baixo acoplamento, onde os módulos funcionam de forma mais independente, facilitando manutenção e reutilização do código.

📍 Classe Anêmica

É uma classe que possui apenas atributos e métodos get e set, sem conter lógica de negócio.
Exemplo: apenas um modelo de dados.

📍 Diagrama UML

Seta vazia e contínua: indica herança. Ex.: "Cachorro é um Animal".

Seta vazia e pontilhada: indica interface. Ex.: "Professor ensina Aluno".

Seta preenchida e contínua: representa associação, como "Carro implementa Veículo".

📍 Débito Técnico

É o resultado de decisões rápidas ou mal planejadas durante o desenvolvimento.
Embora possam resolver problemas no curto prazo, essas decisões geram problemas futuros que exigem correção, aumentando o custo de manutenção.

SOLID

O objetivo dos princípios SOLID é guiar o uso correto da Programação Orientada a Objetos, criando sistemas coesos, desacoplados e flexíveis.

S – Single Responsibility Principle (Princípio da Responsabilidade Única)

Cada classe deve ter apenas um motivo para mudar, ou seja, deve cumprir uma única função.
Isso evita classes complexas e difíceis de manter, deixando o sistema mais organizado.

I – Interface Segregation Principle (Princípio da Segregação de Interface)

Uma classe não deve ser obrigada a implementar métodos que não utiliza.
Ao invés de criar interfaces grandes e genéricas, elas devem ser divididas em interfaces menores e específicas, facilitando a implementação e manutenção.

L – Liskov Substitution Principle (Princípio da Substituição de Liskov)

As subclasses devem poder substituir a classe pai sem alterar o funcionamento do sistema.
Esse princípio garante previsibilidade e evita comportamentos inesperados.

📍 Princípio Aberto/Fechado (Open/Closed Principle)

Uma classe ou módulo deve estar:

Aberto para extensão: permitir adicionar novas funcionalidades.

Fechado para modificação: não alterar código existente, reduzindo o risco de bugs.

Isso garante evolução segura do sistema.

📍 Princípio da Inversão de Dependências (Dependency Inversion Principle)

Módulos de alto nível não devem depender de módulos de baixo nível diretamente.
Ambos devem depender de abstrações (como interfaces).
Isso deixa o sistema mais flexível e facilita trocas de implementação.

📍 Prefira composição a herança

A composição permite combinar objetos para criar funcionalidades.
Já a herança pode gerar dependências rígidas e complexas.
Composição promove flexibilidade e reutilização.

📍 Princípio de Demeter (Lei do Menor Conhecimento)

As classes devem conhecer o mínimo possível umas das outras, reduzindo dependências e evitando acoplamento excessivo.

Arquitetura MVC (Model-View-Controller)

Esse padrão organiza o projeto em três camadas principais:

Model: contém os dados e a lógica de negócio.

View: responsável pela interface com o usuário.

Controller: faz a ponte entre Model e View, processando requisições e respostas.

Exemplo em Swing no Java:

package br.univille;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JOptionPane;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Janelinha extends JFrame {

    private JButton botaozinho;
    private Controlador controlador;

    public Janelinha() {
        setTitle("Eu não acredito");
        setSize(500, 500);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        botaozinho = new JButton("ME CLICA");
        controlador = new Controlador();
        botaozinho.addActionListener(controlador);

        add(botaozinho);
        setVisible(true);
    }

    public static void main(String[] args) {
        new Janelinha();
    }
}

📍 Padrões de Projeto (Design Patterns)

São soluções reutilizáveis para problemas recorrentes no desenvolvimento de software.
Popularizados pelo livro Design Patterns do Gang of Four (GoF).

Classificação:

Criacionais: tratam da criação de objetos.
Ex.: Factory Method, Singleton, Builder.

Estruturais: focam na composição de classes.
Ex.: Adapter, Facade, Decorator.

Comportamentais: definem formas de interação entre objetos.
Ex.: Observer, Strategy, State.

📍 Factory Method

Centraliza a criação de objetos em métodos específicos, evitando alterar várias partes do código quando um tipo de objeto muda.

📍 Singleton

Garante que apenas uma instância de uma classe exista durante a execução do programa.
Exemplo: Logger central para registrar eventos do sistema.

📍 Observer

Estabelece uma relação um-para-muitos, onde um objeto (Subject) notifica outros (Observers) quando seu estado muda.
Exemplo prático: sistema de notificações.

📍 Expectativas de um Arquiteto de Software

Um arquiteto não atua apenas na parte técnica.
Ele também precisa:

Tomar decisões estruturais estratégicas.

Facilitar comunicação entre equipes de desenvolvimento, operações e negócios.

Garantir que o sistema atenda funcionalidades e requisitos de qualidade, como desempenho, segurança e escalabilidade.

📍 Decisões de Arquitetura

Essas decisões são críticas porque moldam a estrutura do sistema e são difíceis de mudar depois.
Envolvem a escolha de:

Padrões arquiteturais.

Tecnologias e frameworks.

Estilos de arquitetura.

Avaliação de trade-offs.

📍 Análise Contínua

O arquiteto deve revisar regularmente a arquitetura, ajustando-a conforme o sistema e o negócio evoluem.
Assim, garante-se que ela continue eficiente e relevante.

📍 Formação do Arquiteto Modelo T

Barra horizontal (conhecimento amplo): domínio geral de várias áreas, como bancos de dados, redes, segurança, DevOps e cloud.

Barra vertical (conhecimento profundo): especialização em áreas específicas, como microsserviços ou performance.

Essa combinação torna o profissional versátil e estratégico.

📍 Trade-off

Cada decisão envolve ganhos e perdas.
O arquiteto deve avaliar cuidadosamente cada escolha para equilibrar:

Desempenho

Segurança

Escalabilidade

Custos

Manutenibilidade

Tempo de entrega

Por exemplo, microsserviços aumentam escalabilidade, mas também a complexidade de operação.

📍 DevOps

Integra desenvolvimento (Dev) e operações (Ops) para acelerar entregas e melhorar qualidade.

Benefícios:

Reduz o tempo de entrega.

Automatiza processos.

Melhora a colaboração.

Aumenta a estabilidade do sistema.

📍 Diferença entre Arquitetura e Design

Arquitetura: trata das decisões estruturais mais amplas e difíceis de mudar.

Design: lida com decisões detalhadas, mais fáceis de modificar, relacionadas à organização interna do código.