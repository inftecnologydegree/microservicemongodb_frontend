# 🏦 Sovereign Bank — DevOps Project 1

Este repositório faz parte de um ecossistema financeiro simulado, construído com foco em **Engenharia DevOps** e **Arquitetura de Software Resiliente**. O projeto consiste em uma aplicação bancária para depósitos e saques que utiliza uma **Arquitetura Desacoplada** para garantir estabilidade, segurança e independência de infraestrutura.

---

## 🗺️ Visão Geral da Arquitetura

O sistema foi dividido em componentes totalmente independentes, eliminando o acoplamento rígido e permitindo que cada camada seja hospedada no provedor de nuvem mais eficiente para o seu propósito.


### 🧱 Divisão dos Componentes

1. **Front-End Estático (Hospedado no GitHub Pages):** Interface de usuário construída puramente em HTML5, CSS3 e JavaScript (Vanilla). Ele consome a API de forma assíncrona.
2. **Back-End REST API (Hospedado no Render):** Servidor construído em Node.js e Express.js responsável pelas regras de negócios, validações financeiras e ponte com a base de dados.
3. **Banco de Dados Relacional (Hospedado no MongoDB Atlas Cloud):** Camada de persistência sólida global que garante que os dados e saldos sobrevivam a reinicializações de servidores na nuvem.

---

## 🏆 Vantagens desta Arquitetura Desacoplada

Implementar essa divisão de responsabilidades traz benefícios críticos de engenharia que mimetizam os ambientes de grandes empresas de tecnologia:

* **Deploys Independentes (Continuous Deployment):** Mudanças no visual ou correções no HTML (Front-End) não exigem que o servidor de dados (Back-End) seja reiniciado ou tirado do ar, reduzindo drasticamente o *Downtime*.
* **Otimização de Custos e Recursos:** O Front-end estático é servido via CDN global gratuita do GitHub Pages, tirando o peso de processamento do servidor Node.js (Render), economizando memória RAM e banda.
* **Sobrevivência do Estado (Persistência Sólida):** Ao mover a gravação de dados da memória volátil ou arquivos locais `.json` para o MongoDB Atlas, mitigamos o problema de servidores efêmeros na nuvem (como os planos gratuitos do Render), garantindo persistência infinita.
* **Escalabilidade Amigável:** Se no futuro este projeto virar um jogo na Unity, um aplicativo mobile em Flutter ou um painel em React, o Back-end continuará exatamente o mesmo. Ele apenas serve dados estruturados em JSON para qualquer cliente autorizado.

---

## 🛡️ Desafios de DevOps Superados neste Projeto

Durante o ciclo de desenvolvimento e implantação em produção, foram resolvidos problemas reais de infraestrutura de redes:

1. **Configuração de Políticas de CORS:** Ajuste fino de cabeçalhos HTTP no Node.js para permitir que domínios externos seguros (GitHub Pages) consumam dados da API.
2. **Segurança de Firewall em Nuvem:** Migração de acesso local seguro de IP para regras de redes distribuídas de provedores dinâmicos através da lista de acesso global (`0.0.0.0/0`) no MongoDB Atlas.
3. **Gestão de Variáveis de Ambiente:** Proteção estrita de credenciais e senhas bancárias usando arquivos de configuração ocultos (`.env`) mapeados de forma nativa e segura no painel do Render.

---

## 🛠️ Tecnologias Utilizadas

* **Front-End:** HTML5, CSS3, JavaScript Avançado (Fetch API / Async-Await).
* **Back-End:** Node.js, Express.js, Mongoose Core, CORS Middleware.
* **Database:** MongoDB Atlas (Cloud Cluster Cluster M0).
* **Infra / DevOps:** Git, GitHub Repositories, Render Cloud, GitHub Pages.

---