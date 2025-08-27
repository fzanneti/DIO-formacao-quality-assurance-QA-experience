# Formação QA Experience

## 3 - Fundamentos de Qualidade de Software

### 3.1 – O que é Qualidade de Software?

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/fundamentals-of-software-quality-and-development-DIO)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![Plataforma](https://img.shields.io/badge/Powered%20by-DIO.io-red?logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB2aWV3Qm94PSIwIDAgMzIgMzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuNzEgMy4yNWMtMi44OCAxLjQxLTUuMDcgNC4yMy01LjA3IDcuNzYgMCAzLjU4IDIuMjggNi43IDUuMzMgOC4xNSAxLjgzLS42MiAyLjQtMi4yNiAyLjQtMy44MSAwLS4yMy0uMDItLjQ1LS4wNS0uNjZBLjQ0LjQ0IDAgMDExMC4xIDExYy4yNC0uNzUuMTEtMS41My0uMy0yLjIyQzguOTIgNy45NiA3LjMzIDcuNSA1Ljc0IDcuNjZhNS41NSA1LjU1IDAgM)
![Autor](https://img.shields.io/badge/Autor-fzanneti-blue?style=flat-square&logo=github)

---

### Introdução

Qualidade de Software é a **capacidade de um sistema atender às necessidades do usuário** de forma confiável, segura, eficiente e sustentável.

Ela está diretamente ligada a fatores como:

* **Funcionalidade**
* **Confiabilidade**
* **Usabilidade**
* **Eficiência**
* **Manutenibilidade**
* **Portabilidade**

---

### Definindo Qualidade

Segundo a **ISO 8402**, qualidade é:

> *“A totalidade das características de uma entidade que lhe confere a capacidade de satisfazer necessidades explícitas e implícitas.”*

Para software, isso significa: entregar **mais do que apenas código funcionando**, mas sim **valor agregado ao cliente**.

---

### Normas e Padrões de Qualidade

* **ISO/IEC 25010 (sucessora da ISO 9126):** define atributos de qualidade de software.
* **IEEE 829:** padrão para documentação de testes.
* **CMMI (Capability Maturity Model Integration):** modelo de maturidade em processos de software.

### 📖 Estudo complementar:

* [ISO/IEC 25010](https://iso25000.com/index.php/en/iso-25000-standards/iso-25010)
* [IEEE Standards](https://standards.ieee.org/)

---

### Medindo Qualidade

A qualidade pode ser medida por **métricas objetivas**, como:

* **Número de defeitos por release.**
* **Taxa de cobertura de testes.**
* **Tempo médio de resolução de bugs.**
* **Disponibilidade do sistema (uptime).**

---

### Processo de Gerenciamento de Qualidade

Envolve 3 pilares:

1. **Planejamento da qualidade** → definição de critérios e métricas.
2. **Garantia da qualidade (QA)** → práticas para assegurar conformidade.
3. **Controle da qualidade (QC)** → execução de testes e monitoramento.

### 📖 Estudo complementar:

* [PMI - Quality Management](https://www.pmi.org/learning/library/project-quality-management-8321)

---

### 3.2 – Gerenciamento de Defeitos

### Falando em Controle de Qualidade

Controle de Qualidade é **detectar falhas** no produto e garantir que o software entregue esteja em conformidade com os requisitos definidos.

---

### Caracterizando Defeitos

Um **defeito** é qualquer divergência entre o software entregue e o comportamento esperado.
Pode se apresentar como:

* **Erro:** ação incorreta cometida pelo desenvolvedor.
* **Defeito (bug):** problema no código.
* **Falha:** quando o sistema apresenta comportamento inesperado em execução.

---

### Ciclo de Vida do Bug

1. **Novo** → bug reportado.
2. **Atribuído** → direcionado a um desenvolvedor.
3. **Em correção** → em progresso.
4. **Resolvido** → correção implementada.
5. **Reaberto** → problema persiste.
6. **Fechado** → confirmado como resolvido.

📌 **Template de bug report (Markdown)**:

```markdown
### Bug Report
**Título:** Checkout falha ao aplicar cupom de desconto  
**Ambiente:** Chrome 120 / Windows 11  
**Passos para reproduzir:**  
1. Adicionar produto ao carrinho  
2. Inserir cupom "DESCONTO10"  
3. Clicar em "Finalizar Compra"  

**Resultado atual:** Erro 500 no servidor  
**Resultado esperado:** Cupom aplicado e compra concluída  
**Severidade:** Alta  
```

---

### Ferramentas de Suporte

* **Jira** → gerenciamento ágil de bugs e tarefas.
* **Azure DevOps** → pipelines + controle de defeitos.
* **Bugzilla** → tradicional para bug tracking.
* **MantisBT** → open source.

📖 Estudo complementar:

* [Jira Software](https://www.atlassian.com/software/jira)
* [Bugzilla](https://www.bugzilla.org/)

---

### 3.3 – Introdução aos Testes de Software

### Conceitos e Objetivos

* **Testes não provam ausência de defeitos, mas reduzem riscos.**
* O objetivo é **verificar se o software atende aos requisitos funcionais e não funcionais**.

---

### Processo de Teste

Etapas principais:

1. **Planejamento** → definir escopo, critérios de aceitação.
2. **Especificação** → escrever casos de teste.
3. **Execução** → rodar testes manuais/automatizados.
4. **Registro** → documentar resultados.
5. **Encerramento** → avaliar métricas e lições aprendidas.

---

### Níveis de Teste

* **Unitário** → valida pequenas partes do código.
* **Integração** → garante que módulos funcionem juntos.
* **Sistema** → valida o software como um todo.
* **Aceitação (UAT)** → realizado pelo cliente/usuário.

---

### Tipos de Teste

* **Funcionais:** caixa preta, regressão, smoke test.
* **Não funcionais:** performance, carga, segurança, usabilidade.
* **Exploratórios:** investigação livre pelo QA.

### 📖 Estudo complementar:

* [Tipos de Testes de Software – Guru99](https://www.guru99.com/types-of-software-testing.html)

---

### Técnicas de Teste

* **Caixa Preta** → sem conhecer código.
* **Caixa Branca** → validando lógica interna.
* **Particionamento de Equivalência.**
* **Análise de Valor Limite.**

📌 Exemplo:
Se o campo "idade" deve aceitar valores de **18 a 60**:

* Casos válidos: 18, 30, 60.
* Casos inválidos: 17, 61.

---

### Conclusão

Testes de software são parte essencial do **processo de qualidade**.
Compreender níveis, tipos e técnicas de testes garante que o QA atue com precisão, prevenindo falhas críticas e elevando a confiabilidade do produto.

### 📖 Estudo complementar:

* [ISTQB Syllabus](https://www.istqb.org/certifications/certified-tester-foundation-level)
* [Software Testing Fundamentals](https://softwaretestingfundamentals.com/)

---

##### ✍️ Criado por: Fabio Zanneti - 🎯 Formação Quality Assurance (QA) Experience
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-181717?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)
