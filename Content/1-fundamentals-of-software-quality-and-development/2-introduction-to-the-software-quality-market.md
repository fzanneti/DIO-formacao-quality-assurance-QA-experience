# Formação QA Experience

## 2 - Introdução ao Mercado de Qualidade de Software

### 2.1 – Mercado e Tendências

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/fundamentals-of-software-quality-and-development-DIO)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![Plataforma](https://img.shields.io/badge/Powered%20by-DIO.io-red?logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB2aWV3Qm94PSIwIDAgMzIgMzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuNzEgMy4yNWMtMi44OCAxLjQxLTUuMDcgNC4yMy01LjA3IDcuNzYgMCAzLjU4IDIuMjggNi43IDUuMzMgOC4xNSAxLjgzLS42MiAyLjQtMi4yNiAyLjQtMy44MSAwLS4yMy0uMDItLjQ1LS4wNS0uNjZBLjQ0LjQ0IDAgMDExMC4xIDExYy4yNC0uNzUuMTEtMS41My0uMy0yLjIyQzguOTIgNy45NiA3LjMzIDcuNSA1Ljc0IDcuNjZhNS41NSA1LjU1IDAgM)
![Autor](https://img.shields.io/badge/Autor-fzanneti-blue?style=flat-square&logo=github)

---

### Introdução

A área de **Qualidade de Software (QA)** está em constante crescimento devido à transformação digital e à necessidade das empresas entregarem **aplicações robustas, seguras e com excelente experiência do usuário**.

Segundo o **World Quality Report**, mais de 60% das organizações aumentaram seus investimentos em **testes e automação de qualidade** nos últimos anos.

---

### Contextualização do Mercado de TI e de QA

* O mercado de TI cresce aceleradamente impulsionado por **IA, cloud, mobile, IoT e automação**.
* A qualidade de software deixou de ser uma etapa final e se tornou **parte essencial do processo de desenvolvimento**.
* Empresas buscam cada vez mais **QAs com visão analítica, técnica e estratégica**.

### 📖 Estudo complementar:

* [World Quality Report 2024-25](https://www.capgemini.com/insights/research-library/world-quality-report-2024-25/)
* [Carreira em QA no Glassdoor](https://www.glassdoor.com.br/Carreira/qa-carreira_KO0,2.htm)

---

### Importância da Qualidade de Software

A qualidade impacta diretamente em:

* **Satisfação do cliente** (ex.: usabilidade, performance).
* **Custo** (falhas em produção são até 100x mais caras do que em desenvolvimento).
* **Imagem da empresa** (bugs graves podem afetar credibilidade).

📌 Exemplo prático:

```gherkin
Scenario: Checkout em e-commerce
  Given que o usuário adicionou produtos ao carrinho
  When ele finaliza a compra
  Then o pagamento deve ser processado corretamente
  And a nota fiscal deve ser gerada
```

Se esse fluxo falha em produção → perda de vendas + imagem arranhada.

---

### O Presente e o Futuro da Área de Qualidade

* **Presente:**

  * Automação de testes (Selenium, Cypress, Playwright).
  * Integração contínua com pipelines (Jenkins, GitHub Actions, GitLab CI).
  * Testes funcionais, não funcionais e de segurança.

* **Futuro:**

  * **IA aplicada em QA** (ex.: geração de casos de teste automáticos com IA).
  * **Testes autônomos** → scripts que se adaptam às mudanças no sistema.
  * **Quality Engineering (QE):** qualidade como prática de engenharia contínua.

### 📖 Estudo complementar:

* [O Futuro do QA com IA – Testim.io](https://www.testim.io/blog/ai-in-testing/)

---

### 2.2 – Afinal, o que faz um QA?

### Engenharia de Software e suas Vertentes

* **Engenharia de Requisitos** → levantamento de necessidades.
* **Engenharia de Testes** → criação de casos e estratégias de teste.
* **Qualidade de Software** → práticas que garantem confiabilidade, performance e usabilidade.

---

### Perfis e Responsabilidades de um QA

* **QA Manual:** executa casos de teste exploratórios, funcionais e de usabilidade.
* **QA Automatizado:** desenvolve scripts e frameworks de automação.
* **SDET (Software Development Engineer in Test):** perfil híbrido entre Dev e QA.
* **Quality Engineer (QE):** atua estrategicamente, garantindo qualidade em todo o ciclo.

📌 Exemplo de **caso de teste automatizado em Cypress**:

```javascript
describe('Login', () => {
  it('Deve fazer login com sucesso', () => {
    cy.visit('/login')
    cy.get('#email').type('usuario@teste.com')
    cy.get('#password').type('senha123')
    cy.get('button[type="submit"]').click()
    cy.url().should('include', '/dashboard')
  })
})
```

### 📖 Estudo complementar:

* [SDET vs QA – Comparação](https://www.guru99.com/sdet-vs-qa.html)
* [Cypress Docs](https://docs.cypress.io/)

---

### O Papel das Certificações na Carreira de QA

* **ISTQB – CTFL (Certified Tester Foundation Level):** mais reconhecida internacionalmente.
* **CTAL (Advanced Level):** níveis mais avançados.
* **Certificações específicas:**

  * Automação: Selenium WebDriver, Cypress.
  * Cloud: AWS/Azure Fundamentals.
  * Ágil: Scrum Master, SAFe.

### 📖 Estudo complementar:

* [ISTQB Official Site](https://www.istqb.org/)

---

### 2.3 – Roadmap de Aprendizagem para Qualidade de Software

### Conhecimentos Técnicos e Conceitos

Para se tornar um QA competitivo:

* **Fundamentos de testes:** caixa preta, caixa branca, smoke test, regressão.
* **Linguagens de programação:** Python, JavaScript, Java, C#.
* **Automação:** Selenium, Cypress, Playwright.
* **APIs:** Postman, Rest Assured.
* **Banco de Dados:** SQL básico (SELECT, JOIN, INSERT, UPDATE).

📌 Exemplo básico de SQL usado em testes:

```sql
-- Validar se usuário foi cadastrado corretamente
SELECT * 
FROM usuarios 
WHERE email = 'usuario@teste.com';
```

📖 Estudo complementar:

* [Guia SQL W3Schools](https://www.w3schools.com/sql/)
* [Playwright Docs](https://playwright.dev/)

---

### Mindset e Soft Skills do QA

Além das habilidades técnicas, o QA precisa de:

* **Mentalidade investigativa** → questionar o sistema.
* **Atenção aos detalhes** → detectar inconsistências.
* **Comunicação clara** → reportar falhas sem atrito.
* **Colaboração** → trabalhar junto a devs, POs, UX.
* **Agilidade** → adaptar-se a mudanças constantes.

---

### Encerramento do Módulo

O QA moderno vai muito além de testes manuais. Ele atua como **engajador de qualidade**, conectando negócios, tecnologia e usuário final.
O roadmap ideal combina **fundamentos de testes, automação, APIs, bancos de dados, cloud, metodologias ágeis e certificações**.

### 📖 Estudo complementar:

* [Roadmap QA Engineer – Roadmap.sh](https://roadmap.sh/qa)

---

##### ✍️ Criado por: Fabio Zanneti - 🎯 Formação Quality Assurance (QA) Experience
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-181717?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)
