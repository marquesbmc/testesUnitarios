

![alt text](https://github.com/marquesbmc/images/blob/main/1-test.jpg)

*<h3 align="right" >"O seu código sempre vai ser testado!" </h3>*

  
## 1. Definição de Teste de Software

De acordo com o Padrão de Teste de Software [ANSI/IEEE 1059](https://www.softwaretestingmaterial.com/international-software-testing-standards/), o Teste em Engenharia de Software é um processo de análise de um produto ou sistema de software para examinar um produto ou sistema de software para determinar se ele satisfaz ou deixa de satisfazer as condições estabelecidas (ou seja, defeitos). O processo de teste avalia as características dos produtos de software quanto a requisitos como requisitos ausentes, bugs ou erros para avaliar sua confiabilidade, segurança e desempenho.

## 2. Tipos de Teste de Software

A engenharia de software já conseguiu categorizar mais de 100 tipos de teste de software, a título de curiosidade o site [https://www.softwaretestingmaterial.com](https://www.softwaretestingmaterial.com/types-of-software-testing/) encontra-se a descrição de sua maioria. 

Elencamos nos tópicos abaixo os principais testes que são importantes para o conhecimento e atenção no que compete o desenvolvimento de software e são largamente requerido nas evolutivas de ambientes.

-  **_Teste unitarios_**: São testes que verificam se uma parte específica do código, costumeiramente a nível de função, está funcionando corretamente. Em um ambiente orientado a objetos é usualmente a nível de classes e a mínima unidade de testes inclui construtores e destrutores. O objetivo do teste unitário é assegurar que cada unidade está funcionando de acordo com sua especificação funcional. Estes tipos de testes são frequentemente escritos por desenvolvedores quando trabalham no código, para assegurar que a função específica está executando como esperado. Uma função deve ter muitos testes para dar cobertura a todos os caminhos possíveis do seu código. Sozinho, o teste unitário não pode verificar a funcionalidade de uma parte do software, mas em contrapartida é usado para assegurar que os blocos constituintes do software trabalham independentes dos demais.

-  **_Teste de integração_**: Visa testar o comportamento de um componente ou a integração entre um conjunto de componentes. Os testes de integração verificam se todo o sistema funciona como pretendido, reduzindo assim a necessidade de testes manuais intensivos. Esses tipos de testes permitem que você traduza suas histórias de usuários em um conjunto de testes. O teste se assemelharia a uma interação esperada do usuário com o aplicativo.

-  **_Teste de interface do usuário_**: Propõe-se a certificar se a interface do usuário do seu aplicativo funciona corretamente. A entrada do usuário deve acionar as ações corretas, os dados devem ser apresentados ao usuário, o estado da interface do usuário deve mudar conforme o esperado.

-  **_Teste de performace_**: É um conjunto de séries de análises voltadas para o desempenho do software mediante várias situações. A partir dos diagnósticos, a equipe é capaz de compreender os limites do programa sob diversas condições.
Para constatar a qualidade da aplicação, ela é submetida a avaliações que simulam eventos e situações previsíveis de acordo com a rotina do cliente, ou seja, testes de carga, estresse e estabilidade. Quaisquer falhas detectadas durante o teste são corrigidas pela equipe precisa e cirurgicamente.

-  **_Teste de segurança_**: Auxiliam a identificar vulnerabilidades e, posteriormente, repará-las. Ajuda a impulsionar o sistema atual e garantir que o sistema funcione por um período prolongado. Para perceber lacunas que causarão perda de informações vitais. É imperativo que os teste de segurança façam parte da Integração Contínua e da Implantação Contínua. 
Para maiores informações consulte https://owasp.org/, no seu top 10 de [maiores vulnerabilidades](https://owasp.org/www-project-top-ten/). 

## 3. A Pirâmide de Teste


<p align="center">
  <img  src="https://github.com/marquesbmc/images/blob/main/test-piramide.png">
</p>

A pirâmide de teste original de Mike Cohn consiste em três camadas nas quais sua suíte de teste deve consistir (de baixo para cima):

-  **_Testes de unidade_**
-  **_Testes de serviço_**
-  **_Testes de interface do usuário_**

Observações Relevantes:

-  **_O que testar?_**: **Você deve escrever testes de software para as partes críticas e complexas do seu aplicativo.** Se você introduzir novos recursos, um conjunto de testes sólido também o protegerá contra a regressão no código existente.

-  **_Não perca tempo!_**: Alguns desenvolvedores acreditam que cada instrução em seu código deve ser testada, mas **em geral é seguro ignorar código trivial.** Por exemplo, normalmente é inútil escrever testes para métodos getter e setter que simplesmente atribuem valores a campos. Escrever testes para essas instruções é demorado e inútil, pois você estaria testando a máquina virtual Java. A própria JVM já possui casos de teste para isso. Se você estiver desenvolvendo aplicativos de usuário final, pode presumir que uma atribuição de campo funciona em Java.

-  **_Automatizar é o caminho?_**:Executar testes automaticamente ajuda a identificar regressões de software introduzidas por alterações no código-fonte. Ter uma **alta cobertura de teste do seu código** permite que você continue desenvolvendo recursos sem ter que realizar muitos testes manuais.

-  **_Onde começar?_**:Se você começar a desenvolver testes para uma base de código existente sem nenhum teste, **é uma boa prática começar a escrever testes para código em que a maioria dos erros ocorreu no passado**. Dessa forma, você pode se concentrar nas partes críticas do seu aplicativo.


[fonte: https://martinfowler.com](https://martinfowler.com/articles/practical-test-pyramid.html)


## 4. Convenções de nomenclatura de classes e métodos de teste

Existem várias convenções de nomenclatura em potencial para testes de software. Uma solução amplamente usada para classes é **usar o sufixo _Test_ ou _Tests_ no final dos nomes das classes de teste.** Essa convenção também é usada pelo sistema de compilação popular para identificar o teste a ser executado.

Como regra geral, um nome de método para um nome deve explicar o que o teste faz. Se isso for feito corretamente, a leitura da implementação real pode ser evitada.

Uma convenção possível é usar o "deveria" no nome do método de teste. Por exemplo, `pedidosDeveSerCriado`ou `menuDeveFicarAtivo`. Isso dá uma dica do que deve acontecer se o método de teste for executado.

Outra abordagem discutida é usar `given[ExplainYourInput]When[WhatIsDone]Then[ExpectedResult]`para o nome de exibição do método de teste. Essa abordagem foi amplamente discutida 
[no Twitter por Uncle Bob](https://twitter.com/unclebobmartin/status/1078664506790707200?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1078664506790707200%7Ctwgr%5E5302043fddf5e7e3c23aad3e1d88dd12eaaaaaba%7Ctwcon%5Es1_&ref_url=https%3A%2F%2Fcdn.embedly.com%2Fwidgets%2Fmedia.html%3Ftype%3Dtext2Fhtmlkey%3Da19fcc184b9711e1b4764040d3dc5c07schema%3Dtwitterurl%3Dhttps3A%2F%2Ftwitter.com%2Funclebobmartin%2Fstatus%2F1078664506790707200image%3Dhttps3A%2F%2Fi.embed.ly%2F1%2Fimage3Furl3Dhttps253A252F252Fpbs.twimg.com252Fprofile_images252F1102364992252Fclean_code_72_color_400x400.png26key3Da19fcc184b9711e1b4764040d3dc5c07).

## 4. JUnit 4


### 4.1. Instalaçao JUnit 4 com Maven
Para usar JUnit em sua compilação do Maven, adicione a seguinte dependência ao seu arquivo pom.
```
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.12</version>
</dependency>
```

### 4.2. Convenções de nomenclatura JUnit para Maven

Se estiver usando o sistema de compilação Maven, você deve usar o sufixo "Test" para classes de teste. O sistema de compilação Maven (por meio de seu plug-in surfire) inclui automaticamente essas classes em seu escopo de teste.

Esta classe pode ser executada como qualquer outro programa Java na linha de comando. Você só precisa adicionar o arquivo JAR da biblioteca JUnit ao caminho de classe.

### 4.3. Definindo métodos de teste

JUnit usa anotações para marcar métodos como métodos de teste e configurá-los. A tabela a seguir fornece uma visão geral das anotações mais importantes no JUnit para as versões 4.xe 5.x. Todas essas anotações podem ser usadas em métodos.

*Tabela 1. Anotações*

| JUnit 4 | Descrição |
|---------|-----------|
| import org.junit.* | Instrução de importação para usar as anotações a seguir. |
| @Test | Identifica um método como um método de teste. |
| @Before | Executado antes de cada teste. Ele é usado para preparar o ambiente de teste (por exemplo, ler dados de entrada, inicializar a classe). |
| @After | Executado após cada teste. Ele é usado para limpar o ambiente de teste (por exemplo, excluir dados temporários, restaurar padrões). Ele também pode economizar memória limpando estruturas de memória caras. |
| @BeforeClass | Executado uma vez, antes do início de todos os testes. Ele é usado para realizar atividades intensivas em tempo, por exemplo, para se conectar a um banco de dados. Os métodos marcados com esta anotação precisam ser definidos `static`para funcionar com JUnit. |
| @AfterClass | Executado uma vez, após a conclusão de todos os testes. Ele é usado para realizar atividades de limpeza, por exemplo, para se desconectar de um banco de dados. Os métodos anotados com esta anotação precisam ser definidos `static`para funcionar com JUnit. |
|@Test (expected = Exception.class)|Falha se o método não lançar a exceção nomeada.|
|@Test(timeout=100)|Falha se o método demorar mais de 100 milissegundos.|
------------------------------------------------------------------------------


### 4.4. Declarações de asserção 

JUnit fornece métodos estáticos para testar determinadas condições por meio da `Assert`classe. Essas **_declarações assert_** geralmente começam com `assert`. Eles permitem que você especifique a mensagem de erro, o resultado esperado e o resultado real. Um _método de asserção_ compara o valor real retornado por um teste com o valor esperado. Ele lança um `AssertionException`se a comparação falhar.

A tabela a seguir fornece uma visão geral desses métodos. Os parâmetros entre colchetes [] são opcionais e do tipo String.


*Tabela 2. Métodos para afirmar os resultados do teste*

| Declaração | Descrição |
|--|--|
| falha([mensagem]) | Deixe o método falhar. Pode ser usado para verificar se uma determinada parte do código não foi alcançada ou para ter um teste com falha antes que o código de teste seja implementado. O parâmetro mensagem é opcional. |
| assertTrue([mensagem,] condição booleana) | Verifica se a condição booleana é verdadeira. |
| assertFalse([mensagem,] condição booleana) | Verifica se a condição booleana é falsa. |
| assertEquals([mensagem,] esperado, real) | Testa se dois valores são iguais. Nota: para arrays a referência é verificada e não o conteúdo dos arrays. |
| assertEquals([mensagem,] esperado, real, tolerância) | Teste se os valores float ou double correspondem. A tolerância é o número de casas decimais que devem ser iguais. |
| assertNull([mensagem,] objeto) | Verifica se o objeto é nulo. |
| assertNotNull([mensagem,] objeto) | Verifica se o objeto não é nulo. |
| assertSame([mensagem,] esperado, real) | Verifica se ambas as variáveis se referem ao mesmo objeto. |
| assertNotSame([mensagem,] esperado, real) | Verifica se ambas as variáveis se referem a objetos diferentes. |

### 4.5. Teste de unidade com JUnit 4

[JUnit](http://junit.org/) é uma estrutura de teste que usa anotações para identificar métodos que especificam um teste. JUnit é um projeto de código aberto hospedado no [Github](https://github.com/junit-team/junit).

_Um teste_ JUnit é um método contido em uma classe que é usado apenas para teste. Isso é chamado **_de classe de teste_** . Para definir que um determinado método é um método de teste, anote-o com a `@Test`anotação.

Este método executa o código em teste. Você usa um método **_assert_** , fornecido pelo JUnit ou outra estrutura assert, para verificar um resultado esperado versus o resultado real. Essas chamadas de método são normalmente chamadas de **_asserts_** ou **_declarações assert_** .

**Você deve fornecer mensagens significativas em declarações assert.** Isso torna mais fácil para o usuário identificar e corrigir o problema. Isso é especialmente verdadeiro se alguém olhar para o problema, que não escreveu o código em teste ou o código de teste.

_Exemplo de teste unitári simples_

O código a seguir mostra um teste JUnit usando a versão JUnit 4.

Suponha que você tenha essa classe que deseja testar.


```
package br.gov.dominio.sixxx;

public class Calculator {

    public int multiply(int a, int b) {
        return a * b;
    }
}
```

Uma classe de teste contendo testes de software para a classe acima pode ter a seguinte aparência.


```
package br.gov.dominio.sixxx;

import static org.junit.Assert.assertEquals;

import org.junit.Before;
import org.junit.Test;

public class CalculatorTest {

    private Calculator calculator;

    @Before
    void setUp() throws Exception {
        calculator = new Calculator();
    }

    @Test
    void testMultiply() {
        assertEquals( "A multiplicação deve funcionar", calculator.multiply(4,5), 20);
    }

    @Test
    void testMultiplyWithZero() {
        assertEquals("Multiplicação com zero deve ser zero",0,  calculator.multiply(0,5));
        assertEquals("Multiplicação com zero deve ser zero", 0, calculator.multiply(5,0));
    }
}
```

### 4.6. Conceito de suítes de teste JUnit

Se você tiver várias classes de teste, poderá combiná-las em um conjunto de testes. A execução de um conjunto de testes executa todas as classes de teste desse conjunto na ordem especificada. Um conjunto de testes também pode conter outros conjuntos de testes.

O código de exemplo a seguir demonstra o uso de um conjunto de testes. Ele contém duas classes de teste (MyClassTest e MySecondClassTest). Se você quiser adicionar outra classe de teste, poderá adicioná-la à `@Suite.SuiteClasses`instrução.

```
package br.gov.dominio.sixxx;

import org.junit.runner.RunWith;
import org.junit.runners.Suite;
import org.junit.runners.Suite.SuiteClasses;

@RunWith(Suite.class)
@SuiteClasses({
        MyClassTest.class,
        MySecondClassTest.class })

public class AllTests {

}
```
### 4.7. Desativando testes

A anotação @Ignore permite ignorar estaticamente um teste. Alternativamente, você pode usar `Assume.assumeFalse`ou `Assume.assumeTrue`para definir uma condição para o teste. `Assume.assumeFalse`marca o teste como inválido, se sua condição for avaliada como verdadeira. `Assume.assumeTrue`avalia o teste como inválido se sua condição for avaliada como falsa. Por exemplo, o seguinte desabilita um teste no Linux:

```
Assume.assumeFalse(System.getProperty("os.name").contains("Linux"));
```

### 4.8.  Teste parametrizado

JUnit permite que você use parâmetros em uma classe de testes. Esta classe pode conter **um** método de teste e este método é executado com os diferentes parâmetros fornecidos.

Você marca uma classe de teste como um teste parametrizado com a `@RunWith(Parameterized.class)`anotação.

Essa classe de teste deve conter um método estático anotado com a `@Parameters`anotação. Esse método gera e retorna uma coleção de arrays. Cada item desta coleção é usado como parâmetro para o método de teste.

Você pode usar a `@Parameter`anotação em campos públicos para obter os valores de teste injetados no teste.

O código a seguir mostra um exemplo para um teste parametrizado. Ele testa o `multiply()`método da `MyClass`classe que está incluída como classe interna para o propósito deste exemplo.

```
package br.gov.dominio.sixxx.testing;

import org.junit.Test;
import org.junit.runner.RunWith;
import org.junit.runners.Parameterized;
import org.junit.runners.Parameterized.Parameters;

import java.util.Arrays;
import java.util.Collection;

import static org.junit.Assert.assertEquals;
import static org.junit.runners.Parameterized.*;

@RunWith(Parameterized.class)
public class ParameterizedTestFields {

    // fields used together with @Parameter must be public
    @Parameter(0)
    public int m1;
    @Parameter(1)
    public int m2;
    @Parameter(2)
    public int result;


    // creates the test data
    @Parameters
    public static Collection<Object[]> data() {
        Object[][] data = new Object[][] { { 1 , 2, 2 }, { 5, 3, 15 }, { 121, 4, 484 } };
        return Arrays.asList(data);
    }


    @Test
    public void testMultiplyException() {
        MyClass tester = new MyClass();
        assertEquals("Result", result, tester.multiply(m1, m2));
    }


    // class to be tested
    class MyClass {
        public int multiply(int i, int j) {
            return i *j;
        }
    }

}
```

Como alternativa ao uso da `@Parameter`anotação, você pode usar um construtor no qual armazena os valores de cada teste. O número de elementos em cada array fornecido pelo método anotado `@Parameters` deve corresponder ao número de parâmetros no construtor da classe. A classe é criada para cada parâmetro e os valores de teste são passados por meio do construtor para a classe.

.

```
package br.gov.dominio.sixxx.testing.junit.first;

import static org.junit.Assert.assertEquals;

import java.util.Arrays;
import java.util.Collection;

import org.junit.Test;
import org.junit.runner.RunWith;
import org.junit.runners.Parameterized;
import org.junit.runners.Parameterized.Parameters;

@RunWith(Parameterized.class)
public class ParameterizedTestUsingConstructor {

    private int m1;
    private int m2;

    public ParameterizedTestUsingConstructor(int p1, int p2) {
        m1 = p1;
        m2 = p2;
    }

    // creates the test data
    @Parameters
    public static Collection<Object[]> data() {
        Object[][] data = new Object[][] { { 1 , 2 }, { 5, 3 }, { 121, 4 } };
        return Arrays.asList(data);
    }


    @Test
    public void testMultiplyException() {
        MyClass tester = new MyClass();
        assertEquals("Result", m1 * m2, tester.multiply(m1, m2));
    }


    // class to be tested
    class MyClass {
        public int multiply(int i, int j) {
            return i *j;
        }
    }

}
```
Se você executar esta classe de teste, o método de teste será executado com cada parâmetro definido. No exemplo acima, o método de teste é executado três vezes.

Uma abordagem mais flexível e fácil de escrever é fornecida pelo JUnitParams de [https://github.com/Pragmatists/JUnitParams](https://github.com/Pragmatists/JUnitParams) .

### 4.7. Regras JUnit

Por meio de regras JUnit, você pode adicionar comportamento a cada teste em uma classe de teste. Você pode anotar campos do tipo `TestRule`com a `@Rule`anotação. Você pode criar objetos que podem ser usados e configurados em seus métodos de teste. Isso adiciona mais flexibilidade aos seus testes. Você pode, por exemplo, especificar qual mensagem de exceção você espera durante a execução do seu código de teste.

```
package br.gov.dominio.sixxx.testing.junit.first;

import org.junit.Rule;
import org.junit.Test;
import org.junit.rules.ExpectedException;

public class RuleExceptionTesterExample {

  @Rule
  public ExpectedException exception = ExpectedException.none();

  @Test
  public void throwsIllegalArgumentExceptionIfIconIsNull() {
    exception.expect(IllegalArgumentException.class);
    exception.expectMessage("Negative value not allowed");
    ClassToBeTested t = new ClassToBeTested();
    t.methodToBeTest(-1);
  }
}
```

JUnit já fornece várias implementações de regras úteis. Por exemplo, a `TemporaryFolder`classe permite configurar arquivos e pastas que são removidos automaticamente após cada execução de teste.

O código a seguir mostra um exemplo para o uso da `TemporaryFolder`implementação.

```
package br.gov.dominio.sixxx.testing.junit.first;

import static org.junit.Assert.assertTrue;

import java.io.File;
import java.io.IOException;

import org.junit.Rule;
import org.junit.Test;
import org.junit.rules.TemporaryFolder;

public class RuleTester {

  @Rule
  public TemporaryFolder folder = new TemporaryFolder();

  @Test
  public void testUsingTempFolder() throws IOException {
    File createdFolder = folder.newFolder("newfolder");
    File createdFile = folder.newFile("myfilefile.txt");
    assertTrue(createdFile.exists());
  }
}
```

Para obter mais exemplos de regras existentes, consulte [https://github.com/junit-team/junit4/wiki/Rules](https://github.com/junit-team/junit4/wiki/Rules) .

### 4.7.  Escrevendo regras JUnit personalizadas

Para escrever sua regra personalizada, você precisa implementar a `TestRule`interface. Esta interface define o `apply(Statement, Description)`método que deve retornar uma instância de `Statement`. A instrução representa os testes dentro do tempo de execução do JUnit e Statement#evaluate() os executa. Descrição descreve o teste individual. Permite ler informações sobre o teste via reflexão.

Veja a seguir um exemplo simples para adicionar uma instrução de log a um aplicativo Android antes e depois da execução do teste.

```
package br.gov.dominio.sixxx.testing.junit.asynctask;

import android.util.Log;

import org.junit.rules.TestRule;
import org.junit.runner.Description;
import org.junit.runners.model.Statement;

public class MyCustomRule implements TestRule {
    private Statement base;
    private Description description;

    @Override
    public Statement apply(Statement base, Description description) {
        this.base = base;
        this.description = description;
        return new MyStatement(base);
    }

    public class MyStatement extends Statement {
        private final Statement base;

        public MyStatement(Statement base) {
            this.base = base;
        }

        @Override
        public void evaluate() throws Throwable {
            System.
            Log.w("MyCustomRule",description.getMethodName() + "Started" );
            try {
                base.evaluate();
            } finally {
                Log.w("MyCustomRule",description.getMethodName() + "Finished");
            }
        }
    }
}
```

Para usar essa regra, basta adicionar um campo anotado `@Rule`à sua classe de teste.

```
@Rule
public MyCustomRule myRule = new MyCustomRule();
```

### 4.8.  Categorias 

É possível definir categorias de testes e incluí-los ou excluí-los com base em anotações. O exemplo a seguir é baseado nas [notas de versão do JUnit 4.8](https://github.com/junit-team/junit/blob/master/doc/ReleaseNotes4.8.md) .

```
public interface FastTests { /* category marker */
}

public interface SlowTests { /* category marker */
}

public class A {
    @Test
    public void a() {
        fail();
    }

    @Category(SlowTests.class)
    @Test
    public void b() {
    }
}

@Category({ SlowTests.class, FastTests.class })
public class B {
    @Test
    public void c() {
    }
}

@RunWith(Categories.class)
@IncludeCategory(SlowTests.class)
@SuiteClasses({ A.class, B.class })
// Note that Categories is a kind of Suite
public class SlowTestSuite {
    // Will run A.b and B.c, but not A.a
}

@RunWith(Categories.class)
@IncludeCategory(SlowTests.class)
@ExcludeCategory(FastTests.class)
@SuiteClasses({ A.class, B.class })
// Note that Categories is a kind of Suite
public class SlowTestSuite {
    // Will run A.b, but not A.a or B.c
}
```

### 4.9.  Importações estáticas JUnit

A importação estática é um recurso que permite que campos e métodos definidos em uma classe `public static`sejam usados sem especificar a classe na qual o campo está definido.

As instruções de assert JUnit são normalmente definidas `public static`para permitir que o desenvolvedor escreva instruções de teste curtas. O trecho a seguir demonstra uma instrução assert com e sem importações estáticas.
.

```
// without static imports you have to write the following statement
Assert.assertEquals("10 x 5 must be 50", 50, tester.multiply(10, 5));


// alternatively define assertEquals as static import
import static org.junit.Assert.assertEquals;

// more code

// use assertEquals directly because of the static import
assertEquals("10 x 5 must be 50", 50, tester.multiply(10, 5));
```
### 5.0.  Show me code!

Exemplo teste

![alt text](https://github.com/marquesbmc/images/blob/main/test-tree-code.png)


<h4>
package br.com.dominio.sixxx.main
<h4>
</h4>
