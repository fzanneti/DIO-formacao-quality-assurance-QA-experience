# Formação QA Experience

## 2 - Testes Unitários com JUnit

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/fundamentals-of-software-quality-and-development-DIO)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![Plataforma](https://img.shields.io/badge/Powered%20by-DIO.io-red?logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB2aWV3Qm94PSIwIDAgMzIgMzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuNzEgMy4yNWMtMi44OCAxLjQxLTUuMDcgNC4yMy01LjA3IDcuNzYgMCAzLjU4IDIuMjggNi43IDUuMzMgOC4xNSAxLjgzLS42MiAyLjQtMi4yNiAyLjQtMy44MSAwLS4yMy0uMDItLjQ1LS4wNS0uNjZBLjQ0LjQ0IDAgMDExMC4xIDExYy4yNC0uNzUuMTEtMS41My0uMy0yLjIyQzguOTIgNy45NiA3LjMzIDcuNSA1Ljc0IDcuNjZhNS41NSA1LjU1IDAgM)
![Autor](https://img.shields.io/badge/Autor-fzanneti-blue?style=flat-square&logo=github)

Este módulo apresenta os **testes unitários** utilizando o **JUnit 5**, uma biblioteca essencial para testes em Java. Ele cobre a importância dos testes, como estruturá-los, recursos avançados, boas práticas e integração com ferramentas modernas, com foco no papel do QA em 2025, incluindo tendências como IA e CI/CD.

---

## 2.1 - Apresentação

### Introdução

**Testes unitários** verificam o comportamento de unidades isoladas de código (ex.: métodos, classes), garantindo qualidade e confiabilidade. O **JUnit 5** é a biblioteca padrão para testes em Java, amplamente adotada em projetos ágeis e DevOps.

**Papel do QA**: Escrever e manter testes unitários para validar lógica de negócio, detectar erros precocemente e documentar o comportamento esperado.

**Tendência 2025**: Uso de ferramentas de IA (ex.: Testim, GitHub Copilot) para sugerir casos de teste e otimizar a cobertura.

---

### Estudo Complementar:

🔗[JUnit 5 User Guide](https://junit.org/junit5/docs/current/user-guide/)  
🔗[Testim - Automação com IA](https://www.testim.io/) 

---

## 2.2 - Por que Escrever Testes Unitários?

### Benefícios:

- **Detecção Precoce de Erros**: Identifica bugs antes da integração.  
- **Prevenção de Regressão**: Garante que alterações não quebrem funcionalidades existentes.  
- **Confiança no Código**: Permite refatorações seguras.  
- **Documentação Viva**: Testes descrevem o comportamento esperado. 

---

### Exemplo:

- **Sem Testes**:  

  ```java

  public class Calculadora {
      public int somar(int a, int b) {
          return a + b; // Erro potencial: e se mudar para a * b?
      }
  }

  ```

* Uma alteração acidental pode passar despercebida.  

- **Com Testes (JUnit 5)**:  

  ```java

  import org.junit.jupiter.api.Test;
  import static org.junit.jupiter.api.Assertions.*;

  class CalculadoraTest {
      @Test
      void deveSomarDoisNumerosPositivos() {
          Calculadora calc = new Calculadora();
          assertEquals(5, calc.somar(2, 3), "2 + 3 deve retornar 5");
      }
  }

  class Calculadora {
      int somar(int a, int b) {
          return a + b;
      }
  }

  ```

* O teste falha se a lógica for alterada incorretamente.

---

### Estudo Complementar:

🔗[Baeldung - JUnit 5 Tutorial](https://www.baeldung.com/junit-5)  

---

## 2.3 - Hello World, JUnit!

Um exemplo inicial com **JUnit 5**:

```java

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class HelloWorldTest {
    @Test
    void deveRetornarMensagemCorreta() {
        String mensagem = "Hello, JUnit!";
        assertEquals("Hello, JUnit!", mensagem, "Mensagem deve ser igual");
    }
}

```

### Como Executar:

- **Maven**: `mvn test`  
- **Gradle**: `gradle test`  
- **IDE**: Clique direito no arquivo > *Run As JUnit Test* (Eclipse) ou `Ctrl + Shift + F10` (IntelliJ).  

---

## 2.4 - Aprofundando nos Recursos do JUnit 5

### Asserções Básicas

```java

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class BasicAssertionsTest {
    @Test
    void testAssercoesBasicas() {
        assertEquals(10, 5 + 5, "5 + 5 deve ser 10");
        assertTrue(5 > 2, "5 é maior que 2");
        assertFalse(2 > 5, "2 não é maior que 5");
        assertNotNull("Texto", "String não deve ser nula");
    }
}

```

---

### Before e After

Usado para configurar e limpar o ambiente de teste.

```java

import org.junit.jupiter.api.*;

class LifecycleTest {
    @BeforeEach
    void init() {
        System.out.println("Preparando ambiente para teste...");
    }

    @AfterEach
    void tearDown() {
        System.out.println("Limpando ambiente após teste...");
    }

    @Test
    void testExemplo() {
        assertEquals(2, 1 + 1, "1 + 1 deve ser 2");
    }
}

```

---

### Assumptions

Permite executar testes apenas em condições específicas.

```java

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assumptions.*;

class AssumptionsTest {
    @Test
    void testApenasEmAmbienteDeDev() {
        assumeTrue("DEV".equals(System.getenv("AMBIENTE")), "Teste executado apenas em DEV");
        assertEquals(2, 1 + 1);
    }
}

```

---

### Testando Exceções

```java

import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

class ExceptionTest {
    @Test
    void deveLancarArithmeticException() {
        Exception exception = assertThrows(ArithmeticException.class, () -> {
            int resultado = 10 / 0;
        });
        assertEquals("/ by zero", exception.getMessage());
    }
}

```

---

### Ordenando Testes

```java

import org.junit.jupiter.api.*;

@TestMethodOrder(MethodOrderer.OrderAnnotation.class)
class OrderedTests {
    @Test
    @Order(1)
    void primeiroTeste() {
        System.out.println("Executando primeiro teste");
        assertTrue(true);
    }

    @Test
    @Order(2)
    void segundoTeste() {
        System.out.println("Executando segundo teste");
        assertTrue(true);
    }
}

```

---

### Parametrização

Permite executar o mesmo teste com diferentes entradas.

```java

import org.junit.jupiter.params.ParameterizedTest;
import org.junit.jupiter.params.provider.CsvSource;
import static org.junit.jupiter.api.Assertions.*;

class ParametrizedTest {
    @ParameterizedTest
    @CsvSource({"1, 2, 3", "5, 5, 10", "-1, 1, 0"})
    void testSoma(int a, int b, int esperado) {
        Calculadora calc = new Calculadora();
        assertEquals(esperado, calc.somar(a, b));
    }
}

class Calculadora {
    int somar(int a, int b) {
        return a + b;
    }
}

```

---

### Estudo Complementar:
  
🔗[JUnit Pioneer](https://junit-pioneer.org/)  
🔗[JaCoCo - Cobertura de Código](https://www.jacoco.org/)  

---

## 2.5 - Recursos de Testes nas IDEs

### Visual Studio Code

- **Extensão**: **Extension Pack for Java**, **Test Runner for Java**.  
- **Atalho**: `Ctrl + F5` para rodar testes.  
- **Funcionalidade**: Exibe resultados com cobertura diretamente no editor.  

---

### Eclipse

- **Execução**: Clique direito no arquivo > *Run As > JUnit Test*.  
- **Recurso**: Interface gráfica com logs detalhados e navegação para falhas.  

---

### IntelliJ IDEA
- **Atalho**: `Ctrl + Shift + F10` (Windows/Linux).  
- **Recurso**: Relatórios visuais com gráficos, cobertura de código e integração com Git.  

---

### Estudo Complementar:

🔗[GitHub Codespaces](https://docs.github.com/pt/codespaces)  

---

## 2.6 - Integração com CI/CD

Testes unitários são executados automaticamente em pipelines CI/CD para garantir qualidade contínua.

---

### Estudo Complementar:

🔗[GitHub Actions](https://docs.github.com/pt/actions)  

---

## 2.7 - Boas Práticas

- **Testes Pequenos e Claros**: Teste uma única funcionalidade por método.  
- **Nomenclatura Descritiva**: Use nomes como `deveValidarCPFValido` ou `deveLancarExcecaoParaEntradaInvalida`.  
- **Independência**: Testes não devem depender de outros testes.  
- **Cenários de Sucesso e Falha**: Cubra casos positivos, negativos e limites.  
- **Automação no CI/CD**: Execute testes automaticamente em cada commit.  
- **Cobertura de Código**: Use ferramentas como JaCoCo para garantir cobertura mínima (ex.: 80%).  

---

## 2.8 - Tabela de Ferramentas

| **Categoria**            | **Ferramentas**                              | **Uso**                              |
|--------------------------|----------------------------------------------|--------------------------------------|
| Testes Unitários         | JUnit 5, TestNG, Mockito                    | Validação de lógica interna           |
| Cobertura de Código      | JaCoCo, Clover, SonarQube                   | Análise de cobertura de testes       |
| CI/CD                    | GitHub Actions, Jenkins, Azure Pipelines    | Automação de testes                  |
| IDEs                     | IntelliJ IDEA, VS Code, Eclipse             | Execução e depuração de testes       |
| IA no QA                 | Testim, Mabl, GitHub Copilot                | Geração de testes automatizada       |

---

## 2.9 - Conclusão

- **Testes unitários com JUnit 5** são fundamentais para garantir a qualidade de aplicações Java.  
- Eles reduzem custos de manutenção, previnem regressões e servem como documentação.  
- Em 2025, QAs devem integrar testes em pipelines CI/CD, usar ferramentas de cobertura (ex.: JaCoCo) e explorar IA para otimizar testes.  
- Boas práticas, como nomenclatura descritiva e independência de testes, são essenciais para sistemas robustos.  

---

## Links de Estudo

🔗[Documentação Oficial JUnit 5](https://junit.org/junit5/docs/current/user-guide/)  
🔗[Baeldung - JUnit 5 Tutorial](https://www.baeldung.com/junit-5)  
🔗[Testes Unitários com JUnit - Alura](https://www.alura.com.br/artigos/testes-unitarios-com-junit)  
🔗[JaCoCo - Cobertura de Código](https://www.jacoco.org/)  
🔗[GitHub Actions](https://docs.github.com/pt/actions)  
🔗[GitHub Copilot](https://github.com/features/copilot)  
🔗[Ministry of Testing - Comunidade](https://www.ministryoftesting.com/)  

---

##### ✍️ Criado por: Fabio Zanneti - 🎯 Formação Quality Assurance (QA) Experience
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-181717?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)