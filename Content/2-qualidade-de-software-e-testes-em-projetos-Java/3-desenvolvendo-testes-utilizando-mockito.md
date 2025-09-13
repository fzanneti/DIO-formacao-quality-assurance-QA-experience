# Formação QA Experience

## 3 - Desenvolvendo Testes Utilizando Mockito

![GitHub repo size](https://img.shields.io/github/repo-size/fzanneti/fundamentals-of-software-quality-and-development-DIO)
![GitHub forks](https://img.shields.io/github/forks/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![GitHub Repo stars](https://img.shields.io/github/stars/fzanneti/fundamentals-of-software-quality-and-development-DIO?style=social)
![Plataforma](https://img.shields.io/badge/Powered%20by-DIO.io-red?logo=data:image/svg+xml;base64,PHN2ZyBmaWxsPSIjZmZmIiB2aWV3Qm94PSIwIDAgMzIgMzIiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+PHBhdGggZD0iTTYuNzEgMy4yNWMtMi44OCAxLjQxLTUuMDcgNC4yMy01LjA3IDcuNzYgMCAzLjU4IDIuMjggNi43IDUuMzMgOC4xNSAxLjgzLS42MiAyLjQtMi4yNiAyLjQtMy44MSAwLS4yMy0uMDItLjQ1LS4wNS0uNjZBLjQ0LjQ0IDAgMDExMC4xIDExYy4yNC0uNzUuMTEtMS41My0uMy0yLjIyQzguOTIgNy45NiA3LjMzIDcuNSA1Ljc0IDcuNjZhNS41NSA1LjU1IDAgM)
![Autor](https://img.shields.io/badge/Autor-fzanneti-blue?style=flat-square&logo=github)

Este módulo apresenta o **Mockito**, uma biblioteca essencial para criar **mocks** e **spies** em testes unitários com Java. Ele cobre a criação de testes isolados, manipulação de comportamentos, boas práticas e integração com ferramentas modernas, com foco no papel do QA em 2025, incluindo tendências como IA e CI/CD.

---

### 3.1 - Apresentação

- O **Mockito** é uma biblioteca poderosa para criar **mocks** (objetos simulados) e **spies** (objetos reais com comportamento parcial simulado), permitindo testes unitários **rápidos, confiáveis e independentes** de dependências externas, como bancos de dados ou APIs.
- **Papel do QA**: Usar Mockito para isolar lógica de negócio, validar interações e garantir qualidade em projetos Java, especialmente em pipelines CI/CD.
- **Tendência 2025**: Integração com ferramentas de IA (ex.: GitHub Copilot) para gerar mocks automaticamente a partir de especificações.

---

### Estudo Complementar:  

🔗[Documentação Oficial Mockito](https://site.mockito.org/)  
🔗[GitHub Copilot](https://github.com/features/copilot)  

---

### 3.2 - Introdução ao Mockito

**O que é um Mock?**

Um **mock** é um objeto simulado que imita o comportamento de uma dependência real, permitindo testar uma classe isoladamente.   
Utilizamos **mocks** quando queremos obter respostas esperadas de objetos que compõem nossos testes mas sem necessariamente utilizar de algum recurso. Por exemplo: chamadas para APIs, Bancos de Dados.
Para criar um mock, usamos na classe que desejamos "mockar" a anotação `@Mock` e para injetar esse mock na classe que estamos testando utilizamos a anotação `@InjectMocks`.

---

**Benefícios**:  

- Evita chamadas a serviços externos (ex.: APIs, bancos).  
- Acelera testes (sem I/O).  
- Simula cenários complexos (ex.: falhas de rede). 

---

A anotação `@ExtendWith(MockitoExtension.class)` é necessária para a integração do Mockito com o JUnit 5.

---

**Exemplo Simples**:  

```java

import org.junit.jupiter.api.Test;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;

class MockitoIntroTest {
    @Test
    void deveRetornarValorMockado() {
        List<String> listaMock = mock(List.class);
        when(listaMock.get(0)).thenReturn("Mockito funcionando!");

        assertEquals("Mockito funcionando!", listaMock.get(0));
    }
}

```

---

### Estudo Complementar:

🔗[Baeldung - Mockito Tutorial](https://www.baeldung.com/mockito-series)  

---

### 3.3 - Mockando Objetos

Mocks isolam dependências, permitindo testar a lógica de uma classe sem interagir com sistemas reais.

**Exemplo Completo**:  

```java

class ServicoEmail {
    boolean enviar(String mensagem) {
        return true; // Simula envio de email
    }
}

class Usuario {
    private final ServicoEmail servico;

    Usuario(ServicoEmail servico) {
        this.servico = servico;
    }

    boolean notificar(String msg) {
        return servico.enviar(msg);
    }
}

import org.junit.jupiter.api.Test;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;

class UsuarioTest {
    @Test
    void deveNotificarComSucesso() {
        ServicoEmail servicoMock = mock(ServicoEmail.class);
        when(servicoMock.enviar("Olá, QA!")).thenReturn(true);

        Usuario usuario = new Usuario(servicoMock);
        assertTrue(usuario.notificar("Olá, QA!"));

        verify(servicoMock).enviar("Olá, QA!");
    }

    @Test
    void deveFalharAoNotificarComMensagemNula() {
        ServicoEmail servicoMock = mock(ServicoEmail.class);
        when(servicoMock.enviar(null)).thenThrow(new IllegalArgumentException("Mensagem não pode ser nula"));

        Usuario usuario = new Usuario(servicoMock);
        assertThrows(IllegalArgumentException.class, () -> usuario.notificar(null));
    }
}

```

**Como funciona?**

- **`Mockito.when`(...):** É o método principal do Mockito para configurar o comportamento de um mock. Ele indica "quando" um determinado método for chamado.
- **`objeto.chamaUmMetodo()`:** É a chamada do método que você quer simular. O Mockito intercepta essa chamada.
- **`.thenReturn(2)`:** É o método que define o que a chamada anterior deve retornar. Neste caso, sempre que o método `chamaUmMetodo()` for invocado no objeto mock, ele retornará o valor `2`, em vez de executar a sua lógica original.

> Essa técnica é fundamental em testes de unidade, pois permite isolar a classe que está sendo testada, controlando as dependências dela e garantindo que o teste seja focado apenas na lógica da classe em questão.

---

### 3.4 - Espionando Objetos

Um **spy** é um objeto real que permite sobrescrever comportamentos específicos, mantendo a implementação original quando não mockada.

**Como o @Spy funciona?**

Diferentemente do @Mock, que cria um objeto completamente simulado e sem comportamento real, o @Spy cria uma instância real da classe. Isso significa que:

- **Comportamento Real:** O `spy` executa os métodos da classe normalmente.
- **Monitoramento:** Você pode usar o `spy` para verificar se um método foi chamado e quantas vezes, usando a instrução `verify()`.
- **Sobrescrevendo Comportamento:** Se precisar, você pode simular o comportamento de um método específico no `spy` usando `doReturn()` ou `doThrow()`. Essa é a abordagem recomendada para `spies`, pois o uso de `when()` pode ter efeitos inesperados em alguns casos.

Use `@Spy` quando você quer testar a classe real, mas precisa ter a capacidade de verificar interações ou, em casos específicos, simular o comportamento de métodos que dependem de outras partes do sistema.

---

**Exemplo**:  

```java

import org.junit.jupiter.api.Test;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;

import java.util.ArrayList;
import java.util.List;

class SpyTest {
    @Test
    void deveEspionarLista() {
        List<String> lista = new ArrayList<>();
        List<String> spyLista = spy(lista);

        spyLista.add("QA");
        spyLista.add("Mockito");

        when(spyLista.size()).thenReturn(100);

        assertEquals(100, spyLista.size());
        assertEquals("QA", spyLista.get(0));
        verify(spyLista).add("Mockito");
    }
}

```

```java

import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.extension.ExtendWith;
import org.mockito.InjectMocks;
import org.mockito.Spy;
import org.mockito.junit.jupiter.MockitoExtension;

import java.util.ArrayList;
import java.util.List;

import static org.junit.jupiter.api.Assertions.assertEquals;
import static org.mockito.Mockito.verify;
import static org.mockito.Mockito.when;

@ExtendWith(MockitoExtension.class)
class SpyTestComAnotacao {

    @Spy
    List<String> spyLista = new ArrayList<>();

    @Test
    void deveEspionarLista() {
        spyLista.add("QA");
        spyLista.add("Mockito");

        when(spyLista.size()).thenReturn(100);

        assertEquals(100, spyLista.size());
        assertEquals("QA", spyLista.get(0));
        verify(spyLista).add("Mockito");
    }
}

```

---  

### 3.5 - Capturando Argumentos

O **ArgumentCaptor** permite capturar e inspecionar argumentos passados a métodos mockados.
A anotação `@Captor` permite capturar argumentos de uma chamada utilizando Mockito

---

**Exemplo**:  

```java

import org.junit.jupiter.api.Test;
import org.mockito.ArgumentCaptor;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;

class ArgumentCaptorTest {
    @Test
    void deveCapturarMensagemEnviada() {
        ServicoEmail servicoMock = mock(ServicoEmail.class);
        Usuario usuario = new Usuario(servicoMock);

        usuario.notificar("Mensagem Importante");

        ArgumentCaptor<String> captor = ArgumentCaptor.forClass(String.class);
        verify(servicoMock).enviar(captor.capture());

        assertEquals("Mensagem Importante", captor.getValue());
    }
}

```

```java

import org.junit.jupiter.api.Test;
import org.junit.jupiter.api.extension.ExtendWith;
import org.mockito.ArgumentCaptor;
import org.mockito.Captor;
import org.mockito.junit.jupiter.MockitoExtension;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;

@ExtendWith(MockitoExtension.class)
class ArgumentCaptorWithCaptorTest {

    @Captor
    ArgumentCaptor<String> captor;

    @Test
    void deveCapturarMensagemEnviadaComAnotacao() {
        ServicoEmail servicoMock = mock(ServicoEmail.class);
        Usuario usuario = new Usuario(servicoMock);

        usuario.notificar("Mensagem Importante");

        verify(servicoMock).enviar(captor.capture());

        assertEquals("Mensagem Importante", captor.getValue());
    }
}

```

---

### 3.6 - Manipulando Retornos

O Mockito permite configurar retornos dinâmicos ou sequenciais para chamadas mockadas.

**Exemplo**:  

```java

import org.junit.jupiter.api.Test;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;

class RetornosTest {
    @Test
    void deveRetornarValoresSequenciais() {
        List<String> listaMock = mock(List.class);

        when(listaMock.size()).thenReturn(1).thenReturn(2).thenReturn(3);

        assertEquals(1, listaMock.size());
        assertEquals(2, listaMock.size());
        assertEquals(3, listaMock.size());
    }
}

```

---

### 3.7 - Mockando Métodos Estáticos

- Desde o **Mockito 3.4+**, é possível mockar métodos estáticos usando `MockedStatic`.
- `mockito-inline` essa dependência permite fazer testes de métodos estáticos.

**Exemplo**:

```java

import org.junit.jupiter.api.Test;
import static org.mockito.Mockito.*;
import static org.junit.jupiter.api.Assertions.*;

class Util {
    static String saudacao() {
        return "Olá, mundo!";
    }
}

class StaticMockTest {
    @Test
    void deveMockarMetodoEstatico() {
        try (MockedStatic<Util> mockStatic = mockStatic(Util.class)) {
            mockStatic.when(Util::saudacao).thenReturn("Mockado!");

            assertEquals("Mockado!", Util.saudacao());
            mockStatic.verify(Util::saudacao);
        }
    }
}

```

---

### 3.8 - Conclusão

- **Mockito** é essencial para testes unitários isolados, permitindo simular dependências complexas.  
- Recursos como mocks, spies, capturadores de argumentos e mock de métodos estáticos aumentam a flexibilidade.  
- Em 2025, QAs devem integrar Mockito com CI/CD, usar ferramentas de cobertura (ex.: JaCoCo) e explorar IA para otimizar testes.  
- Boas práticas, como validação de interações e nomenclatura clara, garantem testes robustos e manuteníveis.  

---

### Links de Estudo

🔗[Documentação Oficial Mockito](https://site.mockito.org/)  
🔗[Baeldung - Mockito Tutorial](https://www.baeldung.com/mockito-series)  
🔗[Mockito + JUnit 5 - DigitalOcean](https://www.digitalocean.com/community/tutorials/mockito-tutorial)  
🔗[JaCoCo - Cobertura de Código](https://www.jacoco.org/)  
🔗[GitHub Actions](https://docs.github.com/pt/actions)  
🔗[WireMock - Mocking de APIs](http://wiremock.org/)  
🔗[Ministry of Testing - Comunidade](https://www.ministryoftesting.com/)  

---

##### ✍️ Criado por: Fabio Zanneti - 🎯 Formação Quality Assurance (QA) Experience
[![GitHub](https://img.shields.io/badge/GitHub-fzanneti-181717?style=flat&logo=github)](https://github.com/fzanneti)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-fzanneti-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/fzanneti)