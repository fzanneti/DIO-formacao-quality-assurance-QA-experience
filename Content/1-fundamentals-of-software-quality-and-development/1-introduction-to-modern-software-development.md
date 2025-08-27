# Formação QA Experience

## 1 - Fundamentos de Qualidade e Desenvolvimento de Software

### 1.1 – Introdução ao Desenvolvimento Moderno de Software

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/fundamentals-of-software-quality-and-development-DIO)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![Plataforma](https://img.shields.io/badge/Powered%20by-DIO.io-red?logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB2aWV3Qm94PSIwIDAgMzIgMzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuNzEgMy4yNWMtMi44OCAxLjQxLTUuMDcgNC4yMy01LjA3IDcuNzYgMCAzLjU4IDIuMjggNi43IDUuMzMgOC4xNSAxLjgzLS42MiAyLjQtMi4yNiAyLjQtMy44MSAwLS4yMy0uMDItLjQ1LS4wNS0uNjZBLjQ0LjQ0IDAgMDExMC4xIDExYy4yNC0uNzUuMTEtMS41My0uMy0yLjIyQzguOTIgNy45NiA3LjMzIDcuNSA1Ljc0IDcuNjZhNS41NSA1LjU1IDAgM)
![Autor](https://img.shields.io/badge/Autor-fzanneti-blue?style=flat-square&logo=github)

---

## Introdução

O desenvolvimento moderno de software não se limita a “escrever código”, mas sim a **entregar valor ao usuário** por meio de soluções digitais escaláveis, seguras e de fácil utilização.

Atualmente, o ciclo de vida de software (SDLC) é orientado por:

* **Metodologias Ágeis** → Scrum, Kanban, SAFe.
* **Integração Contínua e Entrega Contínua (CI/CD)**.
* **DevOps** → Integração entre desenvolvimento, QA e operações.
* **Automação** → Testes automatizados, pipelines, deploys.

O papel do QA se encaixa como guardião da qualidade em todas essas etapas, não apenas como testador, mas como um facilitador da entrega de software confiável, escalável e de valor real para o cliente.
O QA moderno participa de todas essas etapas (mentalidade *shift-left testing*), ajudando a prevenir falhas desde o planejamento até a produção.

### 📖 Estudo complementar:

* [Manifesto Ágil](https://agilemanifesto.org/iso/ptbr/manifesto.html)
* [Ciclo de Vida de Software (SDLC)](https://www.geeksforgeeks.org/software-development-life-cycle-sdlc/)

---

## UX/UI Designer

* **UX (User Experience):** experiência do usuário durante a interação.
* **UI (User Interface):** design visual e usabilidade da aplicação.
* **Relação com QA**:
  - QA ajuda a validar se as interfaces entregues correspondem ao protótipo (ex.: testes de usabilidade, acessibilidade e compatibilidade).
  - Exemplo prático: testar se o contraste de cores está adequado para acessibilidade (WCAG).

### 📖 Estudo complementar:

* [W3C - Web Accessibility](https://www.w3.org/WAI/)
* [UX Design - Nielsen Norman Group](https://www.nngroup.com/articles/)

---

## Front End

* **Definição:** camada visível pelo usuário (o "lado do cliente").
* **Tecnologias comuns:** HTML5, CSS3, JavaScript, frameworks como React, Angular, Vue.
* **Desafios para QA:**
  - Testes de responsividade (funciona bem em diferentes tamanhos de tela?).
  - Testes de compatibilidade cross-browser.
  - Testes de performance (carregamento rápido, sem travamentos).

### 📖 Estudo complementar:

* [MDN Web Docs - HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
* [React - Documentação Oficial](https://react.dev/)

---

## Framework

* **O que é:** uma coleção estruturada de ferramentas, bibliotecas e boas práticas que aceleram o desenvolvimento.
* **Exemplos:**
  - Front End: React, Angular, Vue.js
  - Back End: Spring Boot (Java), .NET, Django (Python), Express.js (Node.js)
* **Importância para QA:**
  - Influencia diretamente nas estratégias de teste (cada framework tem particularidades).
  - Exemplo: em React, muitos testes são feitos com Jest + Testing Library.

### 📖 Estudo complementar:

* [Spring Boot (Java)](https://spring.io/projects/spring-boot)
* [.NET (Microsoft)](https://dotnet.microsoft.com/)
* [Angular](https://angular.dev/)

---

## Back End

* **Definição:** a camada responsável pelas regras de negócio, banco de dados e APIs.
* **Tecnologias comuns:** Java, C#, Python, Node.js, Go.
* **Desafios para QA:**
  - Validação de APIs (status codes, payload, autenticação).
  - Testes de segurança (injeções, acessos indevidos).
  - Testes de integração entre serviços.
* **Ferramentas:** Postman, Newman, Rest Assured, JMeter.

### 📖 Estudo complementar:

* [Node.js](https://nodejs.org/)
* [Postman - Ferramenta de Teste de API](https://www.postman.com/)

---

## Full Stack

* **Definição:** O **profissional full stack** transita entre Front End e Back End.
* **Impacto no QA:**
  - QA precisa conhecer um pouco de todo o fluxo: desde a interface até a API e o banco de dados.
  - Testes end-to-end (E2E) são mais relevantes nesse contexto.
* **Exemplo:** validar um fluxo completo de compra em e-commerce:
  - Usuário adiciona item no carrinho (Front End).
  - Sistema processa pedido (Back End).
  - Dados são salvos e retornados ao cliente (Banco + API).

### 📖 Estudo complementar:

* [O que é Full Stack Developer?](https://www.geeksforgeeks.org/what-is-full-stack-development/)

---

## QA (Quality Assurance)

* **Evolução:** deixou de ser apenas “quem encontra bugs” para se tornar um papel estratégico que previne problemas e contribui para a qualidade em todas as etapas.
* **Principais funções:**
  - Definição de critérios de aceitação junto ao time.
  - Criação de testes automatizados e manuais.
  - Validação de requisitos funcionais e não funcionais.
  - Monitoramento de qualidade em produção.
* **Mentalidade moderna:** Shift-left testing → QA participa desde o início do desenvolvimento. Hoje o QA participa desde a concepção, definindo critérios de aceitação, apoiando Devs, e garantindo qualidade contínua.

### 📖 Estudo complementar:

* [ISTQB Foundation Level (CTFL)](https://www.istqb.org/certifications/certified-tester-foundation-level)
* [BDD com Cucumber](https://cucumber.io/docs/guides/overview/)

---

## Infraestrutura

* **Definição:** recursos necessários para rodar e manter uma aplicação (servidores, redes, banco de dados, containers).
* **Papel no QA:**
  - Validação de ambientes (homologação, staging, produção).
  - Testes de resiliência e disponibilidade.
  - Monitoramento de logs e métricas.
* **Ferramentas:** Docker, Kubernetes, Terraform.

### 📖 Estudo complementar:

* [Docker - Documentação Oficial](https://docs.docker.com/)
* [Kubernetes - Introdução](https://kubernetes.io/pt/docs/concepts/overview/)

---

## Cloud

* **Definição:** entrega de serviços de TI via internet (IaaS, PaaS, SaaS).
* **Principais provedores:** AWS, Azure, Google Cloud.
* **Impacto para QA:**
  - Testes em ambientes distribuídos.
  - Escalabilidade e performance em nuvem.
  - Testes de segurança em múltiplos serviços.
* **Exemplo:** validar se uma aplicação escala automaticamente em um pico de acessos.

### 📖 Estudo complementar:

* [AWS - O que é Cloud Computing?](https://aws.amazon.com/pt/what-is-cloud-computing/)
* [Azure Fundamentals](https://learn.microsoft.com/pt-br/azure/?product=popular)

---

## Mobile

* **Definição:** desenvolvimento de aplicações para smartphones e tablets.
* **Desafios de QA:**
  - Testes em múltiplos dispositivos, sistemas e versões (fragmentação).
  - Testes offline/online.
  - Performance (uso de bateria, memória, rede).
* **Ferramentas:** Appium, Espresso (Android), XCTest (iOS).

### 📖 Estudo complementar:

* [Appium - Automação de Testes Mobile](https://appium.io/)
* [Google - Guia de Performance para Apps](https://developer.android.com/topic/performance?hl=pt-br)

---

## Conclusão

O **desenvolvimento moderno de software** é multidisciplinar e integrado.
O QA atua como **elo central da qualidade**, validando desde a experiência do usuário (UX/UI) até a performance e segurança em ambientes cloud.
Para se destacar como QA moderno, é essencial ter **visão holística** do ciclo de vida do software, saber dialogar com diferentes áreas (devs, designers, ops) e adotar ferramentas que permitam automação e monitoramento contínuo.

### 📖 Estudo complementar:

* [DevOps e QA - Atlassian](https://www.atlassian.com/devops/devops-tools/qa)
* [Cultura de Qualidade - ThoughtWorks](https://www.thoughtworks.com/insights/articles/culture-of-quality)

---

##### ✍️ Criado por: Fabio Zanneti - 🎯 Formação Quality Assurance (QA) Experience
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-181717?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)
