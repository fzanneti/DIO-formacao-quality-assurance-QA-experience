# Formação QA Experience

## 1 - Fundamentos de Qualidade e Desenvolvimento de Software

Este documento serve como guia para profissionais de QA (iniciantes a avançados) que desejam compreender o desenvolvimento moderno de software e suas responsabilidades como guardiões da qualidade em todas as etapas do ciclo de vida do software (SDLC). Ele aborda conceitos fundamentais, papéis do QA em diferentes camadas e tendências atuais e recursos para aprendizado contínuo.

---

### 1.1 – Introdução ao Desenvolvimento Moderno de Software

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/fundamentals-of-software-quality-and-development-DIO)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![Plataforma](https://img.shields.io/badge/Powered%20by-DIO.io-red?logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB2aWV3Qm94PSIwIDAgMzIgMzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuNzEgMy4yNWMtMi44OCAxLjQxLTUuMDcgNC4yMy01LjA3IDcuNzYgMCAzLjU4IDIuMjggNi43IDUuMzMgOC4xNSAxLjgzLS42MiAyLjQtMi4yNiAyLjQtMy44MSAwLS4yMy0uMDItLjQ1LS4wNS0uNjZBLjQ0LjQ0IDAgMDExMC4xIDExYy4yNC0uNzUuMTEtMS41My0uMy0yLjIyQzguOTIgNy45NiA3LjMzIDcuNSA1Ljc0IDcuNjZhNS41NSA1LjU1IDAgM)
![Autor](https://img.shields.io/badge/Autor-fzanneti-blue?style=flat-square&logo=github)

---

## Introdução

O desenvolvimento moderno de software vai além de “escrever código”. Trata-se de entregar valor ao usuário por meio de soluções digitais escaláveis, seguras e de fácil utilização. O ciclo de vida do software (SDLC) é orientado por práticas ágeis, automação e colaboração entre equipes, com o QA desempenhando um papel central na garantia da qualidade.

Atualmente, o ciclo de vida de software (SDLC) é orientado por:
- **Metodologias Ágeis**: Scrum, Kanban, SAFe.  
- **Integração Contínua e Entrega Contínua (CI/CD)**: Automação de builds, testes e deploys.  
- **DevOps**: Integração entre desenvolvimento, QA e operações para entregas rápidas e confiáveis.  
- **Automação**: Testes automatizados, pipelines e monitoramento.  
- **Shift-Left Testing**: QA participa desde a concepção, definindo critérios de aceitação e prevenindo defeitos.  
- **Shift-Right Testing**: Monitoramento em produção para identificar problemas reais dos usuários.

* **O papel do QA:** O QA moderno não é apenas um “caçador de bugs”, mas um facilitador da qualidade, colaborando desde o planejamento até a produção.

### 📖 Estudo complementar:

* [Manifesto Ágil](https://agilemanifesto.org/iso/ptbr/manifesto.html)
* [Ciclo de Vida de Software (SDLC)](https://www.geeksforgeeks.org/software-development-life-cycle-sdlc/)

---

## UX/UI Designer

* **UX (User Experience):** Foca na experiência do usuário durante a interação com a aplicação (ex.: facilidade de uso, eficiência).
* **UI (User Interface):** Design visual e usabilidade (ex.: botões, cores, layouts).
* **Relação com QA**: O QA valida se as interfaces entregues correspondem aos protótipos, garantindo usabilidade, acessibilidade (WCAG) e consistência visual com Design Systems (ex.: Material Design).
* **Desafios**
  - Testes de acessibilidade (ex.: contraste de cores, suporte a leitores de tela).
  - Validação de consistência visual em diferentes dispositivos.
  - Testes de usabilidade com usuários reais (ex.: testes A/B).

### 📖 Estudo complementar:

* [W3C - Web Accessibility](https://www.w3.org/WAI/)
* [UX Design - Nielsen Norman Group](https://www.nngroup.com/articles/)

---

## Front End

* **Definição:** Camada visível pelo usuário (client-side), responsável pela interface e interatividade.
* **Tecnologias comuns:**
  - HTML5, CSS3, JavaScript.  
  - Frameworks: React, Angular, Vue.js, Svelte (emergente).  
* **Desafios para QA:**
  - **Responsividade**: Funciona em diferentes tamanhos de tela (mobile, tablet, desktop)?  
  - **Compatibilidade Cross-Browser**: Suporte a Chrome, Firefox, Safari, Edge.  
  - **Performance**: Carregamento rápido, sem travamentos (ex.: tempo de carregamento < 3s).  
  - **Acessibilidade**: Suporte a ARIA (Accessible Rich Internet Applications).
* **Ferramentas**  
  - Lighthouse (performance e acessibilidade).  
  - BrowserStack (testes cross-browser).  
  - Percy/Applitools (testes visuais). 

### 📖 Estudo complementar:

* [MDN Web Docs - HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
* [React - Documentação Oficial](https://react.dev/)

---

## Framework

* **Definição:** Coleção estruturada de ferramentas, bibliotecas e boas práticas que aceleram o desenvolvimento.
* **Exemplos:**
  - Front End: React, Angular, Vue.js, Svelte.
  - Back End: Spring Boot (Java), .NET, Django (Python), FastAPI (Python), Express.js (Node.js).
* **Importância para QA:** Cada framework tem particularidades que influenciam as estratégias de teste. Exemplo: em React, usa-se Jest + Testing Library para testes unitários de componentes; em Spring Boot, Rest Assured para testes de API.

### 📖 Estudo complementar:

* [Spring Boot (Java)](https://spring.io/projects/spring-boot)
* [.NET (Microsoft)](https://dotnet.microsoft.com/)
* [Angular](https://angular.dev/)

---

## Back End

* **Definição:** Camada responsável pelas regras de negócio, banco de dados e APIs (server-side).
* **Tecnologias comuns:** Java, C#, Python, Node.js, Go.
* **Desafios para QA:**
  - Validação de APIs (status codes, payloads, autenticação).  
  - Testes de segurança (ex.: SQL injection, XSS).  
  - Testes de integração entre serviços (ex.: microsserviços).  
  - Testes de carga/estresse para performance.
* **Ferramentas:**
  - Postman/Newman (testes de API).  
  - Rest Assured (testes de API em Java).  
  - JMeter/Locust (testes de carga).  
  - Pact (testes de contrato para microsserviços). 

### 📖 Estudo complementar:

* [Node.js](https://nodejs.org/)
* [Postman - Ferramenta de Teste de API](https://www.postman.com/)

---

## Full Stack

* **Definição:** Profissional que transita entre Front End e Back End, lidando com interface, APIs e banco de dados.
* **Impacto no QA:** O QA full stack valida fluxos completos (end-to-end, E2E), garantindo integração entre camadas.
* **Desafios:**  
  - Testes E2E (ex.: fluxo de compra em e-commerce).  
  - Integração entre serviços (ex.: Front End chamando APIs).  
  - Validação de dados em banco (ex.: consistência após uma transação).  
* **Ferramentas:**  
  - Cypress, Playwright, Selenium (testes E2E).  
  - Postman (validação de APIs).  

### 📖 Estudo complementar:

* [O que é Full Stack Developer?](https://www.geeksforgeeks.org/what-is-full-stack-development/)

---

## QA (Quality Assurance)

* **Definição:** O QA moderno é um papel estratégico que previne defeitos, define critérios de aceitação e garante qualidade em todas as fases do SDLC.  
* **Principais Funções:**  
  - Definir critérios de aceitação com o time.  
  - Criar e executar testes manuais e automatizados.  
  - Validar requisitos funcionais (ex.: funcionalidades) e não funcionais (ex.: performance, segurança).  
  - Monitorar qualidade em produção (shift-right).  
* **Mentalidade Moderna:**  
  - **Shift-Left**: QA participa desde o planejamento, escrevendo casos de teste baseados em requisitos.  
  - **Shift-Right**: Monitoramento de logs e métricas em produção.  
  - **Pirâmide de Testes**: Maior volume de testes unitários, seguido por integração e E2E.  
* **Ferramentas:**  
  - Cucumber (BDD).  
  - TestCafe, Robot Framework (automação).  
  - Prometheus, Grafana (monitoramento).  
* **Métricas de Qualidade:**  
  - Cobertura de testes (>80% para unitários).  
  - Taxa de defeitos (ex.: <5% de bugs em produção).  
  - Tempo médio para resolução de bugs.

### 📖 Estudo complementar:

* [ISTQB Foundation Level (CTFL)](https://www.istqb.org/certifications/certified-tester-foundation-level)
* [BDD com Cucumber](https://cucumber.io/docs/guides/overview/)

---

## Infraestrutura

* **Definição:** Recursos necessários para rodar uma aplicação (servidores, redes, containers, banco de dados).
* **Papel no QA:**
  - Validação de ambientes (homologação, staging, produção).
  - Testes de resiliência e disponibilidade.
  - Monitoramento de logs e métricas.
* **Ferramentas:**
  - Docker, Kubernetes (orquestração).  
  - Terraform (IaC).  
  - Chaos Monkey (Chaos Engineering).

### 📖 Estudo complementar:

* [Docker - Documentação Oficial](https://docs.docker.com/)
* [Kubernetes - Introdução](https://kubernetes.io/pt/docs/concepts/overview/)

---

## Cloud

* **Definição:** Entrega de serviços de TI via internet (IaaS, PaaS, SaaS). 
* **Principais provedores:** AWS, Azure, Google Cloud.
* **Impacto para QA:**
  - Testes em ambientes distribuídos.  
  - Escalabilidade e performance (ex.: auto-scaling).  
  - Segurança em múltiplos serviços (ex.: IAM, criptografia).
* **Ferramentas:**  
  - AWS Device Farm (testes mobile).  
  - Gatling (testes de carga).  
  - AWS Lambda (serverless).  

### 📖 Estudo complementar:

* [AWS - O que é Cloud Computing?](https://aws.amazon.com/pt/what-is-cloud-computing/)
* [Azure Fundamentals](https://learn.microsoft.com/pt-br/azure/?product=popular)

---

## Mobile

* **Definição:** Desenvolvimento de aplicações para smartphones e tablets (iOS, Android).
* **Desafios de QA:**
  - Fragmentação: Múltiplos dispositivos, sistemas e versões.  
  - Testes offline/online (ex.: comportamento sem internet).  
  - Performance: Uso de bateria, memória, rede.  
  - Push notifications e deep links. 
* **Ferramentas:**
  - Appium, Espresso (Android), XCTest (iOS).  
  - BrowserStack, Sauce Labs (testes em dispositivos reais).  
  - Fastlane, Bitrise (CI/CD mobile).

### 📖 Estudo complementar:

* [Appium - Automação de Testes Mobile](https://appium.io/)
* [Google - Guia de Performance para Apps](https://developer.android.com/topic/performance?hl=pt-br)

---

## Tabela de Ferramentas

| **Categoria**            | **Ferramentas**                              | **Uso**                              |
|--------------------------|----------------------------------------------|--------------------------------------|
| Testes de API            | Postman, Newman, Rest Assured               | Validação de endpoints e payloads    |
| Testes E2E              | Cypress, Playwright, Selenium               | Testes de fluxos completos           |
| Testes Mobile           | Appium, Espresso, XCTest                    | Automação em iOS e Android           |
| Testes de Performance    | JMeter, Locust, Gatling                    | Carga e estresse                     |
| Acessibilidade           | Lighthouse, Axe, WAVE                      | Conformidade com WCAG                |
| Monitoramento           | Prometheus, Grafana, New Relic             | Logs e métricas em produção          |
| CI/CD                   | Jenkins, GitHub Actions, Fastlane          | Automação de pipelines               |
| Infraestrutura          | Docker, Kubernetes, Terraform              | Gestão de ambientes                  |
| Testes Visuais          | Percy, Applitools                          | Consistência visual cross-browser    |

---

## Conclusão

O desenvolvimento moderno de software é multidisciplinar, exigindo colaboração entre áreas (devs, designers, ops). O QA atua como elo central, validando desde a experiência do usuário (UX/UI) até a performance e segurança em ambientes cloud. Para se destacar, o QA moderno precisa:  
- **Visão Holística**: Conhecer todo o fluxo do SDLC.  
- **Automação**: Dominar ferramentas como Cypress, Appium e Postman.  
- **Soft Skills**: Comunicação e colaboração para alinhar expectativas com o time.  
- **Aprendizado Contínuo**: Participar de comunidades como Ministry of Testing ou eventos como QA Global Summit.

### 📖 Estudo complementar:

* [DevOps e QA - Atlassian](https://www.atlassian.com/devops/devops-tools/qa)
* [Cultura de Qualidade - ThoughtWorks](https://www.thoughtworks.com/insights/articles/culture-of-quality)

---

##### ✍️ Criado por: Fabio Zanneti - 🎯 Formação Quality Assurance (QA) Experience
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-181717?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)
