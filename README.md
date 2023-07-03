# PesquisaExceptions
1 - O que é uma exception?
Quando ocorre um erro ao executar o código, esses erros podem ser cometidos pelo programador, erros de entradas incorretas ou algo imprevisível. 
2 - O que é o try catch e o finally?
try = instrução permite definir um bloco de código a ser testado quanto a erros enquanto está sendo executado.
catch = instrução permite definir um bloco de código a ser executado, caso ocorra um erro no bloco try.
finally = instrução permite executar o código, após try...catch, independentemente do resultado:
3 - Mostre a hierarquia de exceções.
Throwable
├── Error
│   ├── AssertionError
│   ├── OutOfMemoryError
│   ├── StackOverflowError
│   └── ...
│
└── Exception
    ├── RuntimeException
    │   ├── NullPointerException
    │   ├── IllegalArgumentException
    │   ├── IndexOutOfBoundsException
    │   ├── ArithmeticException
    │   ├── ClassCastException
    │   ├── UnsupportedOperationException
    │   └── ...
    │
    └── ...
A classe “Error” é representada por erros graves que geralmente são causados por problemas no ambiente de execução. Normalmente, não é recomendado tratar esses erros no código, pois indicam problemas sérios no ambiente de execução do programa.
A Classe  “Exception” é uma base para todas as exceções em java que não são erros. Ela possui várias subclasses que representam diferentes tipos de exceções, incluindo “RuntimeExceptions” e suas subclasses. As “RuntimeExceptions” são exceções verificadas que ocorrem durante a execução do programa e geralmente são causadas por erros de programação ou condições imprevistas.
4 - O que é throw/throws?
throw = instrução permite que você crie um erro personalizado.
throwr = instrução é usada junto com um tipo de exceção . 
5 - Como tratar múltiplas exceções?
Uma forma de tratar múltiplas exceções é usando blocos “try-catch” separados ou utilizando o bloco “catch” múltiplas vezes no mesmo bloco “try”.
Ao tratar múltiplas exceções é importante lembrar que a ordem dos blocos “catch” é relevante. É recomendado começar as exceções pelas mais específicas e depois as genéricas. Se as exceções mais genéricas forem colocadas antes das exceções mais específicas, estas últimas nunca serão alcançadas.
6 - Mostre um exemplo de exception no código.
public class DivideNumbers {
    public static double divide(double a, double b) {
        try {
            double result = a / b;
            return result;
        } catch (ArithmeticException e) {
            System.out.println("Erro: Divisão por zero não é permitida!");
            return Double.NaN;
        }
    }
    public static void main(String[] args) {
        double num1 = 10;
        double num2 = 0;
        double resultado = divide(num1, num2);
        if (!Double.isNaN(resultado)) {
            System.out.println("O resultado da divisão é: " + resultado);
        }
    }
}
