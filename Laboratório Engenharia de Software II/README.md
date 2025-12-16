# Laboratório Dirigido: Aplicação Web de Gestão de Tarefas

## 1. Introdução

Este projeto apresenta o desenvolvimento de uma aplicação web para gestão de tarefas, implementada seguindo rigorosamente os padrões e normas estabelecidos para qualidade de software, acessibilidade web, segurança da informação e proteção de dados pessoais. A aplicação foi desenvolvida utilizando tecnologias modernas e boas práticas de engenharia de software.

## 2. Objetivos

O presente trabalho tem como objetivo demonstrar a aplicação prática dos seguintes conceitos e normas:

- **Qualidade de Software**: Implementação seguindo os critérios da ISO/IEC 25010, com ênfase em manutenibilidade, confiabilidade e adequação funcional
- **Acessibilidade Web**: Conformidade com as diretrizes WCAG 2.2 (Web Content Accessibility Guidelines), garantindo que a aplicação seja acessível a todos os usuários
- **Segurança da Informação**: Aplicação das práticas recomendadas pelo OWASP Top 10 (2021), prevenindo vulnerabilidades comuns
- **Proteção de Dados**: Conformidade com a LGPD (Lei Geral de Proteção de Dados), respeitando os princípios de minimização e segurança no tratamento de dados

## 3. Tecnologias e Ferramentas

A aplicação foi desenvolvida utilizando as seguintes tecnologias:

- **Backend**: Python 3.11 com Flask (framework web) e Flask-SQLAlchemy (ORM)
- **Banco de Dados**: PostgreSQL
- **Frontend**: HTML5 semântico e CSS3
- **Testes**: pytest para testes automatizados
- **Controle de Versão**: Git e GitHub
- **Ambiente de Desenvolvimento**: Visual Studio Code no ambiente Windows

## 4. Conformidade com Normas e Padrões

### 4.1 Acessibilidade (WCAG 2.2)

A aplicação foi desenvolvida seguindo os princípios POUR (Perceptível, Operável, Compreensível e Robusto) da WCAG 2.2, nível AA:

- **Contraste de Cores**: Implementação de esquema de cores com contraste mínimo de 4,5:1 para texto normal
- **Navegação por Teclado**: Todos os elementos interativos são acessíveis via teclado, com indicadores de foco visíveis
- **Rótulos e Formulários**: Todos os campos de formulário possuem rótulos associados via atributos `for` e `id`, garantindo compatibilidade com leitores de tela
- **HTML Semântico**: Uso adequado de elementos semânticos (`<header>`, `<main>`, `<section>`, `<form>`, etc.)
- **Link de Pular Conteúdo**: Implementação de link para permitir navegação rápida ao conteúdo principal

### 4.2 Segurança (OWASP Top 10: 2021)

As seguintes práticas de segurança foram implementadas:

- **A01 - Broken Access Control**: Validação de existência de recursos antes de operações (uso de `db.get_or_404()`)
- **A03 - Injection**: Prevenção de SQL Injection através do uso de ORM (SQLAlchemy) com prepared statements
- **A05 - Security Misconfiguration**: Configuração segura utilizando variáveis de ambiente para dados sensíveis
- **Validação de Entrada**: Implementação de validação de dados de entrada para prevenir dados inválidos ou maliciosos

### 4.3 Privacidade (LGPD)

Conformidade com a Lei Geral de Proteção de Dados:

- **Minimização de Dados**: Coleta apenas dos dados essenciais (título da tarefa e status de conclusão)
- **Direito de Exclusão**: Implementação de funcionalidade completa para exclusão de dados pessoais
- **Segurança no Tratamento**: Utilização de conexões seguras e práticas de segurança no armazenamento de dados

### 4.4 Qualidade de Software (ISO/IEC 25010)

A aplicação atende aos seguintes critérios de qualidade:

- **Manutenibilidade**: Código limpo, bem documentado com comentários explicativos, seguindo padrões PEP 8
- **Confiabilidade**: Implementação de testes automatizados (testes unitários e de integração) utilizando pytest
- **Adequação Funcional**: Todas as funcionalidades CRUD (Create, Read, Update, Delete) foram implementadas e testadas

## 5. Arquitetura e Estrutura do Projeto

A aplicação segue uma arquitetura MVC (Model-View-Controller) simplificada:

- **Model**: Classe `Tarefa` utilizando SQLAlchemy ORM para abstração do banco de dados
- **View**: Templates HTML com Jinja2 para renderização dinâmica
- **Controller**: Rotas Flask que processam requisições HTTP e coordenam a lógica de negócio

### 5.1 Estrutura de Diretórios

```
lab_todolist/
├── app.py                 # Aplicação Flask principal com rotas e modelo
├── test_app.py           # Suite de testes automatizados
├── requirements.txt      # Dependências do projeto
├── .gitignore           # Configuração de arquivos ignorados pelo Git
├── README.md            # Documentação do projeto
├── package.json         # Configuração npm (ferramentas front-end)
├── templates/           # Templates HTML
│   ├── base.html        # Template base com estrutura semântica
│   └── index.html       # Página principal da aplicação
└── static/              # Arquivos estáticos
    └── css/
        └── style.css    # Estilos CSS com conformidade WCAG
```

## 6. Funcionalidades Implementadas

A aplicação oferece as seguintes funcionalidades:

1. **Criação de Tarefas**: Formulário para adicionar novas tarefas com validação de entrada
2. **Listagem de Tarefas**: Exibição de todas as tarefas cadastradas
3. **Atualização de Status**: Alternância entre tarefa concluída e não concluída
4. **Exclusão de Tarefas**: Remoção de tarefas do sistema (conforme direito de exclusão da LGPD)
5. **Feedback ao Usuário**: Sistema de mensagens flash para comunicação de sucesso e erros

## 7. Metodologia de Testes

Foi implementada uma suite de testes automatizados utilizando pytest, cobrindo:

- **Testes Funcionais**: Verificação do carregamento correto das páginas
- **Testes de Integração**: Validação da interação entre rotas HTTP e banco de dados
- **Testes de Segurança**: Verificação de validação de entrada e prevenção de dados inválidos
- **Testes de Confiabilidade**: Garantia de que operações críticas funcionam conforme esperado

Os testes utilizam um banco de dados em memória (SQLite) para isolamento e rapidez na execução.

## 8. Configuração e Execução

### 8.1 Pré-requisitos

- Python 3.11 ou superior
- PostgreSQL instalado e configurado
- Git para controle de versão
- Ambiente virtual Python (venv)

### 8.2 Instalação

1. Criar ambiente virtual: `python -m venv venv`
2. Ativar ambiente virtual: `.\venv\Scripts\activate` (Windows)
3. Instalar dependências: `pip install -r requirements.txt`
4. Configurar banco de dados PostgreSQL e criar as tabelas
5. Executar aplicação: `python app.py`

### 8.3 Execução de Testes

Os testes podem ser executados através do comando `pytest` ou `pytest -v` para saída detalhada.

## 9. Justificativas Técnicas

### 9.1 Escolha das Tecnologias

- **Flask**: Framework leve e flexível, adequado para aplicações de pequeno e médio porte, permitindo controle total sobre a estrutura
- **SQLAlchemy ORM**: Abstração do banco de dados que previne SQL Injection através de prepared statements e facilita manutenção
- **PostgreSQL**: Banco de dados relacional robusto e confiável, adequado para aplicações que requerem integridade de dados
- **pytest**: Framework de testes moderno e extensível, com excelente suporte para fixtures e parametrização

### 9.2 Decisões de Design

- **Separação de Responsabilidades**: Código organizado seguindo princípios SOLID, com separação clara entre modelo, visualização e controle
- **Documentação Inline**: Comentários explicativos em todo o código, justificando decisões técnicas e relacionando com normas aplicáveis
- **Validação de Entrada**: Implementação de validação tanto no frontend (HTML5 `required`) quanto no backend (Python), seguindo princípio de defesa em profundidade

## 10. Resultados e Conclusões

A aplicação desenvolvida demonstra a aplicação prática dos conceitos de qualidade de software, acessibilidade, segurança e privacidade de dados. Todas as funcionalidades foram implementadas e testadas, garantindo conformidade com as normas estabelecidas:

- ✅ Conformidade WCAG 2.2 nível AA
- ✅ Proteção contra vulnerabilidades OWASP Top 10
- ✅ Conformidade com princípios da LGPD
- ✅ Atendimento aos critérios de qualidade ISO/IEC 25010

O projeto evidencia a importância de considerar aspectos de qualidade, segurança e acessibilidade desde o início do desenvolvimento, resultando em uma aplicação robusta, segura e acessível.

## 11. Referências

- W3C. (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. https://www.w3.org/WAI/WCAG22/quickref/
- OWASP Foundation. (2021). *OWASP Top 10:2021*. https://owasp.org/www-project-top-ten/
- Brasil. (2018). *Lei Geral de Proteção de Dados Pessoais (LGPD)*. Lei nº 13.709/2018
- ISO/IEC 25010:2011. *Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models*
- Flask Documentation. https://flask.palletsprojects.com/
- SQLAlchemy Documentation. https://docs.sqlalchemy.org/
