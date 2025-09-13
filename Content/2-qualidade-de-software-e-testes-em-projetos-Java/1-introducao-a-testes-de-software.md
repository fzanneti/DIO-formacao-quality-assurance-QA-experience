# Formação QA Experience

## 1 - Introdução a Testes de Software (Java)

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/fundamentals-of-software-quality-and-development-DIO)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![Plataforma](https://img.shields.io/badge/Powered%20by-DIO.io-red?logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB2aWV3Qm94PSIwIDAgMzIgMzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuNzEgMy4yNWMtMi44OCAxLjQxLTUuMDcgNC4yMy01LjA3IDcuNzYgMCAzLjU4IDIuMjggNi43IDUuMzMgOC4xNSAxLjgzLS42MiAyLjQtMi4yNiAyLjQtMy44MSAwLS4yMy0uMDItLjQ1LS4wNS0uNjZBLjQ0LjQ0IDAgMDExMC4xIDExYy4yNC0uNzUuMTEtMS41My0uMy0yLjIyQzguOTIgNy45NiA3LjMzIDcuNSA1Ljc0IDcuNjZhNS41NSA1LjU1IDAgM)
![Autor](https://img.shields.io/badge/Autor-fzanneti-blue?style=flat-square&logo=github)

Este módulo apresenta os **fundamentos de testes de software**, com foco em Java, abordando definições, níveis, técnicas, testes não funcionais e a pirâmide de testes. Ele é voltado para QAs iniciantes ou experientes, com exemplos práticos, ferramentas modernas e tendências de 2025, como IA em testes e integração com CI/CD.

---

## 1.1 - Introdução

Os **testes de software** são essenciais no desenvolvimento moderno, garantindo: 

- **Funcionalidade correta**: O sistema atende aos requisitos.  
- **Detecção precoce de bugs**: Evita problemas em produção.  
- **Redução de custos**: Corrigir defeitos em desenvolvimento é até 100x mais barato que em produção.  

---

### Estudo Complementar:  

🔗[Foundations of Software Testing - ISTQB](https://www.amazon.com.br/dp/8131526360)  
🔗[Testim - Automação com IA](https://www.testim.io/)  

---

## 1.2 - Definição e Conceitos Básicos

### Definição de Testes

Teste de software é o processo de **avaliar a qualidade** de um sistema, verificando se ele **atende aos requisitos** e identificando **defeitos** antes da entrega.

* **Papel do QA**: Garantir que o sistema seja confiável, funcional e atenda às expectativas do cliente.

---

### Evolução de Testes na Engenharia de Software

- **Década de 70**: Testes manuais no final do ciclo (Waterfall).  
- **Anos 90**: Crescimento da automação com ferramentas como JUnit.  
- **2025**: Testes contínuos em pipelines CI/CD, integração com DevOps e uso de IA para otimizar estratégias de teste.  

---

### Conceitos Básicos

- **Bug**: Defeito no código que causa comportamento incorreto.  
- **Erro**: Ação humana que gera um defeito (ex.: lógica incorreta).  
- **Falha**: Resultado visível de um bug (ex.: sistema trava).  
- **Risco**: Probabilidade de um defeito causar impacto (ex.: falha em pagamento).  

--- 

### Estudo Complementar:  

🔗[ISTQB Glossary](https://glossary.istqb.org/)  

---

## 1.3 - Níveis e Técnicas de Testes

### Níveis de Teste

1. **Teste Unitário**: Testa componentes isolados (ex.: métodos, classes).  
2. **Teste de Integração**: Verifica interação entre módulos (ex.: API + banco).  
3. **Teste de Sistema**: Avalia o software completo.  
4. **Teste de Aceitação**: Confirma se o sistema atende às necessidades do cliente.  

---

### Técnicas de Teste

- **Caixa-Preta**: Foca em entradas e saídas, sem conhecer o código.  
  - Ex.: Particionamento de equivalência, análise de valor limite, tabela de decisão.  
- **Caixa-Branca**: Analisa a estrutura interna do código.  
  - Ex.: Cobertura de instrução, decisão, caminhos.  
- **Baseado em Experiência**: Testes exploratórios guiados pela intuição do QA.  

---

### Estudo Complementar:

🔗[JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/)  
🔗[Mockito - Documentação](https://site.mockito.org/)  

---

## 1.4 - Testes Não Funcionais

Testes não funcionais avaliam **atributos de qualidade**, como performance, segurança e usabilidade.

### Principais Tipos:

- **Performance**: Tempo de resposta, carga, estresse (ex.: sistema suporta 10.000 usuários simultâneos?).  
- **Segurança**: Autenticação, autorização, proteção contra vulnerabilidades (ex.: SQL injection).  
- **Usabilidade**: Facilidade de uso (ex.: conformidade com WCAG para acessibilidade).  
- **Compatibilidade**: Funcionamento em diferentes sistemas, navegadores ou dispositivos.  

---

### Ferramentas:  

- **JMeter**: Testes de carga e estresse.  
- **OWASP ZAP**: Análise de vulnerabilidades.  
- **Lighthouse**: Performance e acessibilidade.  
- **Snyk**: Segurança de dependências.  

---

### Estudo Complementar:

- [Apache JMeter](https://jmeter.apache.org/)  
- [OWASP ZAP](https://www.zaproxy.org/)  
- [Snyk - Segurança](https://snyk.io/)  

---

## 1.5 - A Pirâmide de Testes

A **pirâmide de testes**, proposta por Mike Cohn, orienta a distribuição de testes para otimizar custo e eficiência.

---

### Estrutura:

- **Base**: **Testes Unitários** (70%) – Rápidos, baratos, cobrem lógica interna.  
- **Meio**: **Testes de Integração** (20%) – Validam interação entre componentes.  
- **Topo**: **Testes de UI/E2E** (10%) – Simulam uso real, mas são lentos e caros.  

---

### Estudo Complementar:

🔗[Pirâmide de Testes - Martin Fowler](https://martinfowler.com/bliki/TestPyramid.html)  
🔗[Playwright - Documentação](https://playwright.dev/)  

---

## 1.6 - Tendências em Testes (2025)

- **IA no QA**: Ferramentas como Testim e Mabl usam IA para gerar casos de teste, detectar anomalias e otimizar cobertura.  
- **DevSecOps**: Integração de testes de segurança (ex.: Snyk, OWASP ZAP) em pipelines CI/CD.  
- **Testes em Cloud**: Uso de plataformas como AWS Device Farm para testes em dispositivos reais.  
- **Low-Code/No-Code**: Validação de plataformas como OutSystems, exigindo testes visuais e de fluxos.  

---

### Estudo Complementar:

🔗[Mabl - Testes com IA](https://www.mabl.com/)  
🔗[AWS Device Farm](https://aws.amazon.com/device-farm/)  

---

## 1.7 - Conclusão

- Testes de software são cruciais para **qualidade**, **redução de custos** e **satisfação do cliente**.  
- Os **níveis de teste** (unitário, integração, sistema, aceitação) cobrem diferentes aspectos do sistema.  
- **Técnicas** (caixa-preta, caixa-branca, exploratório) e **testes não funcionais** garantem robustez.  
- A **pirâmide de testes** orienta a estratégia, com foco em testes rápidos e baratos.  
- Em 2025, QAs devem dominar ferramentas modernas (ex.: Playwright, Snyk) e integrar testes em pipelines CI/CD.  

---

### Links de Estudo:

🔗[JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/)  
🔗[Pirâmide de Testes - Martin Fowler](https://martinfowler.com/bliki/TestPyramid.html)  
🔗[OWASP ZAP - Ferramenta de Segurança](https://www.zaproxy.org/)  
🔗[Apache JMeter](https://jmeter.apache.org/)  
🔗[Playwright - Documentação](https://playwright.dev/)  
🔗[Snyk - Segurança](https://snyk.io/)  
🔗[Ministry of Testing - Comunidade](https://www.ministryoftesting.com/)  

---

##### ✍️ Criado por: Fabio Zanneti - 🎯 Formação Quality Assurance (QA) Experience
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-181717?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)