# 🧸 Brinka

> Loja virtual de action figures desenvolvida com JavaScript Vanilla, Spring Boot e PostgreSQL, com foco em acessibilidade, inclusão e experiência do usuário.

## 📋 Sobre o projeto

O **Brinka** é uma loja virtual de action figures desenvolvida como MVP para a disciplina de **Desenvolvimento de Aplicações Dinâmicas (DAD)**.

O projeto tem como principal diferencial a **acessibilidade digital**, buscando proporcionar uma experiência de compra mais inclusiva, intuitiva e autônoma para diferentes perfis de usuários.

A aplicação integra um **frontend em JavaScript Vanilla**, um **backend desenvolvido em Spring Boot com Java 21** e um **banco de dados PostgreSQL**, além de utilizar Redis para persistência do carrinho e uma API externa para consulta de CEP.

O projeto foi desenvolvido considerando os requisitos técnicos da atividade e os critérios de acessibilidade baseados na **WCAG 2.1 AA**.

---

## 🎯 Objetivo

Desenvolver um MVP funcional de e-commerce capaz de demonstrar, de ponta a ponta:

* Construção de interfaces dinâmicas com JavaScript Vanilla;
* Integração entre frontend e backend;
* Persistência de dados;
* Autenticação e autorização;
* Gerenciamento de produtos;
* Carrinho de compras;
* Experiência responsiva;
* Recursos de acessibilidade;
* Organização e modularização do código.

O projeto busca demonstrar que acessibilidade pode fazer parte da experiência principal do produto, e não apenas ser adicionada posteriormente.

---

## 💡 Problema

Experiências de comércio eletrônico nem sempre são desenvolvidas considerando usuários que dependem de tecnologias assistivas ou possuem diferentes necessidades de interação.

Problemas como:

* falta de estrutura semântica;
* baixo contraste;
* navegação inadequada por teclado;
* elementos sem descrição;
* formulários pouco acessíveis;
* dependência exclusiva de cores;
* dificuldade de navegação por tecnologias assistivas;

podem dificultar ou até impedir a utilização de uma loja virtual.

---

## 💡 Solução

O Brinka busca reduzir essas barreiras por meio de uma loja virtual que combina:

* Interface responsiva;
* HTML semântico;
* Navegação por teclado;
* Compatibilidade com leitores de tela;
* Contraste adequado;
* Textos alternativos;
* Navegação por voz;
* Persistência de preferências e dados;
* Fluxos de compra estruturados.

A acessibilidade é tratada como parte da experiência do produto e não como uma funcionalidade isolada.

---

# ✨ Funcionalidades

## 🛍️ Catálogo

* Catálogo dinâmico com mais de 8 produtos;
* Carregamento dos produtos através da API;
* Filtro por categoria;
* Visualização de informações dos produtos;
* Página de detalhes do produto;
* Exibição de imagem, nome, descrição e preço.

## 🔎 Produtos

O usuário pode:

* Visualizar produtos disponíveis;
* Filtrar produtos por categoria;
* Acessar os detalhes de um produto;
* Consultar informações relacionadas ao produto;
* Avaliar produtos.

## 🛒 Carrinho

O carrinho permite:

* Adicionar produtos;
* Remover produtos;
* Alterar quantidade;
* Visualizar quantidade de itens;
* Calcular o total;
* Manter os dados do carrinho durante a sessão.

A persistência do carrinho utiliza **Redis**.

## 👤 Autenticação

O sistema possui:

* Cadastro de usuário;
* Login;
* Logout;
* Sessão persistente;
* Autenticação utilizando JWT;
* Proteção de rotas;
* Controle de acesso às funcionalidades autenticadas.

## ❤️ Favoritos

Usuários autenticados podem:

* Adicionar produtos aos favoritos;
* Remover produtos dos favoritos;
* Consultar seus produtos favoritos.

## ⭐ Avaliações

O sistema possui suporte a avaliações de produtos.

Os usuários podem consultar avaliações associadas aos produtos e realizar avaliações conforme as regras implementadas na aplicação.

## 📍 Endereços

Usuários autenticados podem cadastrar e gerenciar seus endereços.

A aplicação utiliza uma **API externa de consulta de CEP** para auxiliar no preenchimento dos dados de endereço.

## 📦 Histórico de pedidos

Usuários autenticados podem consultar o histórico de seus pedidos realizados.

---

# ♿ Acessibilidade

A acessibilidade é um dos principais pilares do Brinka.

O desenvolvimento considera os princípios da **WCAG 2.1 AA**, buscando garantir que o sistema possa ser utilizado por pessoas com diferentes necessidades.

### Recursos implementados

* HTML semântico;
* Navegação por teclado;
* Compatibilidade com leitores de tela;
* Textos alternativos (`alt`) para imagens;
* Contraste adequado;
* Foco e interação acessíveis;
* Não utilização exclusiva de cores para transmitir informações;
* Suporte a zoom de até 200%;
* Estrutura hierárquica de títulos;
* Formulários estruturados;
* Labels associados aos campos;
* Recursos de navegação por voz;
* Elementos interativos acessíveis.

### Navegação por voz

O Brinka possui recursos de navegação por voz para facilitar a interação com a aplicação.

Entre as possibilidades de interação estão comandos para:

* Navegar pela aplicação;
* Acionar elementos da interface;
* Interagir com produtos;
* Utilizar funcionalidades do carrinho;
* Acessar áreas da aplicação.

A navegação por voz é um recurso adicional. As funcionalidades principais continuam disponíveis por mouse, toque, teclado e tecnologias assistivas.

### Tecnologias assistivas

Durante o desenvolvimento foram considerados recursos de:

* Leitores de tela;
* Navegação por teclado;
* Comandos de voz;
* Estrutura semântica;
* Foco e identificação adequada dos elementos.

---

# 📱 Responsividade

A interface foi desenvolvida para diferentes tamanhos de tela, contemplando:

* **360px** — dispositivos móveis;
* **768px** — tablets;
* **1280px** — desktops.

Foram realizados testes de responsividade para verificar:

* Ausência de overflow horizontal;
* Redimensionamento dos componentes;
* Organização dos produtos;
* Navegação;
* Formulários;
* Carrinho;
* Elementos interativos.

---

# 🏗️ Arquitetura

O projeto é dividido em componentes independentes, permitindo separar as responsabilidades entre interface, regras de negócio, persistência e dados.

```text
                         ┌─────────────────────┐
                         │      Usuário        │
                         └──────────┬──────────┘
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │      Frontend       │
                         │ HTML + CSS + JS     │
                         │    Vanilla JS       │
                         │  (Render — Docker)  │
                         └──────────┬──────────┘
                                    │
                              HTTP / REST
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │      Backend        │
                         │   Spring Boot      │
                         │      Java 21        │
                         │  (Render — Docker)  │
                         └──────────┬──────────┘
                                    │
                   ┌────────────────┴────────────────┐
                   │                                 │
                   ▼                                 ▼
          ┌─────────────────┐              ┌─────────────────┐
          │   PostgreSQL    │              │      Redis      │
          │ Dados da        │              │ Carrinho        │
          │ aplicação       │              │ (Render interno)│
          └─────────────────┘              └─────────────────┘

                                    │
                                    ▼
                         ┌─────────────────────┐
                         │    APIs externas    │
                         │        CEP          │
                         └─────────────────────┘
```

---

# 📦 Repositórios do projeto

O desenvolvimento foi organizado em diferentes repositórios dentro da organização do projeto.

O repositório **`brinkampv`** funciona como ponto central de entrega e documentação do MVP.

### Frontend

Repositório responsável pela interface da aplicação, desenvolvido com HTML, CSS e JavaScript Vanilla.

[brinka-frontend](https://github.com/AcessibilidadeRodolfo/brinka-frontend)

### Backend

Repositório responsável pela API, regras de negócio, autenticação e integração com os bancos de dados.

[brinka-api](https://github.com/AcessibilidadeRodolfo/brinka-api)

### Banco de dados

Repositório responsável pelos scripts e estrutura do banco PostgreSQL.

[brinka-database](https://github.com/AcessibilidadeRodolfo/brinka-database)

### Documentação

Repositório destinado à documentação e materiais complementares do projeto.

[brinka-docs](https://github.com/AcessibilidadeRodolfo/brinka-docs)

### Pesquisa de acessibilidade

Repositório contendo a pesquisa sobre casos reais de acessibilidade em empresas.

[Pesquisa — Acessibilidade e casos reais](https://github.com/AcessibilidadeRodolfo/pesquisa-acessibilidade-casos-reais-de-empresa-mesa-3)

---

# 🛠️ Tecnologias utilizadas

## Frontend

* HTML5;
* CSS3;
* JavaScript Vanilla;
* ES Modules;
* DOM API;
* Fetch API;
* Local Storage;
* Tecnologias de acessibilidade do navegador;
* Recursos de reconhecimento/navegação por voz.

## Backend

* Java 21;
* Spring Boot;
* Spring Web;
* Spring Data;
* JWT;
* Gradle.

## Banco e persistência

* PostgreSQL;
* Redis.

## API externa

* API de consulta de CEP.

## Infraestrutura e deploy

* **Render** — hospedagem do frontend, do backend e do Redis;
* **Docker** — frontend e backend publicados no Render a partir de `Dockerfile` próprio de cada repositório;
* **Redis interno do Render** — instância privada, acessível apenas pelos serviços do próprio projeto no Render (sem exposição pública).

---

# 🚀 Aplicação

A aplicação está publicada no **Render**, com o frontend e o backend implantados via **Dockerfile** e o Redis provisionado como **serviço interno do Render** (utilizado exclusivamente pelo backend, sem acesso público).

* **Frontend:** [https://brinka-frontend.onrender.com](https://brinka-frontend.onrender.com)
* **Backend / API:** [https://brinka-api.onrender.com](https://brinka-api.onrender.com)
* **Redis:** instância interna do Render, provisionada junto ao backend e não acessível externamente.

---

# 💻 Manual técnico — Execução local

## Pré-requisitos

Para executar o projeto localmente, é necessário possuir:

* Git;
* Java 21;
* PostgreSQL;
* Redis;
* Python;
* Navegador moderno;
* Variáveis de ambiente configuradas no backend.

> Em produção, o frontend e o backend são executados no **Render** a partir dos respectivos `Dockerfile`, e o Redis utilizado é uma **instância interna do Render**. As instruções abaixo descrevem apenas a execução local, sem Docker.

---

## 1. Clonar os repositórios

Clone os repositórios do frontend e backend:

```bash
git clone https://github.com/AcessibilidadeRodolfo/brinka-frontend.git
git clone https://github.com/AcessibilidadeRodolfo/brinka-api.git
```

Clone também o repositório do banco para obter os scripts necessários:

```bash
git clone https://github.com/AcessibilidadeRodolfo/brinka-database.git
```

---

## 2. Configurar o banco PostgreSQL

Certifique-se de que o PostgreSQL esteja instalado e em execução.

Utilize os scripts disponíveis no repositório:

[brinka-database](https://github.com/AcessibilidadeRodolfo/brinka-database)

Execute os scripts necessários para:

1. Criar o banco;
2. Criar as tabelas;
3. Criar as estruturas necessárias;
4. Inserir os dados iniciais.

---

## 3. Configurar o Redis

Certifique-se de que o Redis esteja instalado e executando localmente.

O Redis é utilizado para persistência e gerenciamento do carrinho de compras.

Em produção, o Redis é provisionado como **serviço interno do Render**, associado ao backend implantado via Docker.

---

## 4. Configurar o Backend

Entre na pasta da API:

```bash
cd brinka-api
```

Configure as variáveis de ambiente necessárias.

O arquivo `.env` **não deve ser versionado**.

Utilize o arquivo `.env.example` como referência para criar a configuração local.

Entre as informações necessárias estão as configurações relacionadas ao:

* PostgreSQL;
* Redis;
* JWT;
* demais serviços utilizados pela API.

---

## 5. Executar o Backend

O backend utiliza **Java 21** e Gradle.

No Windows:

```powershell
.\gradlew.bat bootRun
```

Ou:

```powershell
.\gradlew bootRun
```

A API ficará disponível na porta configurada pela aplicação.

Em produção, o backend é publicado no **Render** a partir do `Dockerfile` do repositório `brinka-api`, disponível em: [https://brinka-api.onrender.com](https://brinka-api.onrender.com)

---

## 6. Executar o Frontend

Entre na pasta do frontend:

```bash
cd brinka-frontend
```

O frontend deve ser executado através de um servidor HTTP local.

Uma alternativa simples é utilizar Python:

```bash
python -m http.server 5500
```

Depois acesse:

```text
http://localhost:5500
```

Não é recomendado abrir o `index.html` diretamente pelo protocolo `file://`, pois a aplicação utiliza módulos JavaScript e comunicação com a API.

Em produção, o frontend é publicado no **Render** a partir do `Dockerfile` do repositório `brinka-frontend`, disponível em: [https://brinka-frontend.onrender.com](https://brinka-frontend.onrender.com)

---

# 📖 Manual do usuário

## 1. Acessar a loja

Ao acessar a aplicação, o usuário encontra o catálogo de action figures disponíveis.

Os produtos são carregados dinamicamente e apresentados na interface principal.

---

## 2. Encontrar um produto

O usuário pode utilizar o filtro de categoria para encontrar produtos de acordo com o tipo desejado.

Também é possível navegar pelo catálogo e selecionar um produto para consultar seus detalhes.

---

## 3. Visualizar detalhes

Ao selecionar um produto, são apresentadas informações como:

* Nome;
* Imagem;
* Descrição;
* Preço;
* Outras informações disponíveis.

---

## 4. Adicionar ao carrinho

Para comprar um produto:

1. Selecione o produto;
2. Acesse seus detalhes;
3. Escolha a opção de adicionar ao carrinho.

O produto será incluído no carrinho.

---

## 5. Gerenciar o carrinho

No carrinho é possível:

* Aumentar a quantidade;
* Diminuir a quantidade;
* Remover produtos;
* Visualizar o total da compra.

O carrinho possui persistência utilizando Redis.

---

## 6. Criar uma conta

Para utilizar funcionalidades que exigem autenticação:

1. Acesse a área de cadastro;
2. Preencha os dados solicitados;
3. Envie o formulário;
4. Após o cadastro, realize o login.

---

## 7. Fazer login

O usuário informa suas credenciais cadastradas.

Após a autenticação, a aplicação cria uma sessão utilizando JWT.

A sessão permanece disponível de acordo com as regras definidas pela aplicação.

---

## 8. Favoritos

Usuários autenticados podem marcar produtos como favoritos.

Os produtos favoritos podem ser consultados posteriormente para facilitar o acesso aos itens de interesse.

---

## 9. Avaliar produtos

Após acessar um produto, o usuário pode consultar as avaliações disponíveis e utilizar o recurso de avaliação quando estiver autenticado e atender às regras da aplicação.

---

## 10. Cadastrar endereço

O usuário pode cadastrar um endereço de entrega.

Durante o preenchimento, o CEP pode ser consultado por meio da API externa para auxiliar na obtenção dos dados de localização.

---

## 11. Histórico de pedidos

Usuários autenticados podem consultar seus pedidos realizados através da área correspondente da aplicação.

---

# 🔌 Integração Frontend → Backend

O frontend (publicado no Render em [https://brinka-frontend.onrender.com](https://brinka-frontend.onrender.com)) realiza requisições HTTP para a API desenvolvida em Spring Boot, publicada no Render em [https://brinka-api.onrender.com](https://brinka-api.onrender.com).

O fluxo principal é:

```text
Usuário
   ↓
Interface JavaScript (Render — Docker)
   ↓
Fetch API
   ↓
Spring Boot REST API (Render — Docker)
   ↓
Regras de negócio
   ↓
PostgreSQL / Redis interno (Render)
```

O frontend não acessa diretamente o banco de dados.

As informações são solicitadas através da API, mantendo a separação entre apresentação, regras de negócio e persistência.

---

# 🔐 Autenticação e segurança

A autenticação utiliza **JWT**.

O fluxo básico é:

```text
Cadastro
   ↓
Login
   ↓
API valida credenciais
   ↓
JWT
   ↓
Frontend mantém sessão
   ↓
Requisições autenticadas
   ↓
Backend valida token
```

As rotas protegidas exigem autenticação.

Credenciais e informações sensíveis não devem ser armazenadas diretamente no frontend.

---

# 🗄️ Banco de dados

O PostgreSQL é utilizado para persistência dos principais dados da aplicação.

Entre os dados persistidos estão informações relacionadas a:

* Usuários;
* Produtos;
* Pedidos;
* Avaliações;
* Endereços;
* Demais entidades necessárias ao funcionamento da aplicação.

O Redis é utilizado para o gerenciamento e persistência do carrinho, sendo provisionado em produção como **serviço interno do Render**, sem exposição pública, acessível apenas pelo backend.

A modelagem e os scripts do banco estão disponíveis no repositório:

[brinka-database](https://github.com/AcessibilidadeRodolfo/brinka-database)

---

# 🧪 Acessibilidade e Lighthouse

A acessibilidade foi validada utilizando os critérios definidos na atividade e ferramentas de auditoria.

Foram realizadas **3 execuções do Lighthouse**, seguindo o protocolo definido:

* Chrome em janela anônima;
* Sem extensões;
* Categoria Acessibilidade;
* Dispositivo Desktop;
* Três execuções consecutivas;
* Utilização da mediana dos resultados.

Os resultados completos estão disponíveis em:

[`lighthouse-report.md`](./lighthouse-report.md)

Os testes apresentaram resultados satisfatórios de acessibilidade e responsividade.

---

# 📊 Evidências

O repositório principal reúne as principais evidências necessárias para avaliação do MVP:

* README;
* Relatório Lighthouse;
* Documentação;
* Referências aos repositórios do projeto;
* Manual técnico;
* Manual do usuário.

---

# 👥 Integrantes

| Integrante      | Responsabilidade              |
| --------------- | ----------------------------- |
| **Rahquel**     | Prototipação UI/UX e Figma    |
| **Erick**       | Frontend — HTML e CSS         |
| **João**        | Frontend — JavaScript Vanilla |
| **Vini**        | Backend                       |
| **Mari**        | Modelagem do banco de dados   |
| **João & Mari** | Documentação                  |

A divisão de responsabilidades representa o foco principal de cada integrante. O projeto foi desenvolvido de forma colaborativa, e todos os integrantes devem conhecer o funcionamento geral da aplicação para a arguição técnica.

---

# 📌 Organização do projeto

O desenvolvimento foi organizado em repositórios separados por responsabilidade.

Essa divisão permite:

* Separação entre frontend e backend;
* Organização do banco de dados;
* Centralização da documentação;
* Desenvolvimento paralelo;
* Controle independente das diferentes partes da aplicação.

O `brinkampv` funciona como o **repositório agregador da entrega**, reunindo documentação, evidências e referências para todos os componentes do projeto.

---

# 🤖 Uso de Inteligência Artificial

Ferramentas de Inteligência Artificial, incluindo **ChatGPT, Claude e outras ferramentas de IA**, foram utilizadas durante o desenvolvimento como recursos de apoio.

A IA foi utilizada principalmente para:

* Revisão de código;
* Identificação de possíveis erros;
* Sugestões de melhorias;
* Apoio na implementação de funcionalidades;
* Pesquisa e aprendizado de tecnologias que não haviam sido abordadas em sala;
* Revisão de acessibilidade;
* Organização da documentação;
* Apoio na resolução de problemas técnicos;
* Discussão de decisões de implementação.

A responsabilidade pelo desenvolvimento permaneceu com os integrantes da equipe.

O código gerado ou sugerido por ferramentas de IA foi analisado, compreendido, adaptado e integrado pelos próprios integrantes.

A equipe é responsável pelas decisões técnicas e pelo funcionamento final do sistema.

---

# 🚧 Implementações futuras

O projeto possui funcionalidades que podem ser desenvolvidas posteriormente, entre elas:

* Área administrativa;
* Docker Compose;
* Cupons de desconto;
* Cálculo de frete;
* Melhorias na infraestrutura de deploy;
* Expansão dos recursos de gerenciamento de produtos;
* Novas funcionalidades de acessibilidade;
* Melhorias de testes automatizados;
* Evolução das integrações externas.

Essas funcionalidades não fazem parte do escopo atual do MVP.

---

# 📄 Entrega

Este projeto faz parte da atividade de **MVP de Desenvolvimento de Aplicações Dinâmicas (DAD)**.

A entrega contempla:

* MVP funcional;
* Repositório público;
* README;
* Manual técnico;
* Manual do usuário;
* Relatório Lighthouse;
* Documentação;
* Apresentação em formato pitch;
* Versionamento do projeto.

## Versão da apresentação

A versão utilizada para a apresentação será identificada por uma tag de versão, como:

```text
v1.0-pitch
```

---

## 📜 Licença

Este projeto foi desenvolvido para fins acadêmicos. Está sobe a licença MIT.
