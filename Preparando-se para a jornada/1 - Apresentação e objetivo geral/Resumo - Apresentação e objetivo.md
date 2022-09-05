# Apresentação e objetivo geral

### Apresentação

Objetivo aqui é compreender a metodologia educacional de um bootcamp DIO, passando por todos os seus elementos, com o objetivo de impulsionar o seu protagonismo nessa jornada !

### Percurso

Parte 1 
Bootcamp Dio (Explicando metodologia de ensino).

Parte 2 
Desafios de código (Entendendo na prática).

Parte 3 
Desafios de projeto (Entendendo na prática).

Parte 4
Dicas finais e conclusão

---

## Desvendando os bootcamps DIO

### Metodologia de ensino

Principais tipos de conteúdos educacionais :

- Cursos (Conceitos essenciais e fundamentação teórica).
- Mentorias (Imersão tecnológica/ cultural interativa.
- Desafios de código (Lógica e pensamento computacional)
- Desafios de projeto (prática e criação de portifólio).

### Fóruns

Temos 2 opções :

- Usar o Room (Postagens direcionadas para o bootcamp que estamos).
- Usar o Forum geral (Postagens gerais direcionadas a todos os estudantes da DIO).

---

### Desafios de código

> “Falar é fácil. Mostre-me o código !” Linus Torvalds (Elaborador do kernel Linux).
> 

### Desafio de Java

Questão 

Voce receberá dois valores inteiros. Faça a leitura e em seguida calcule o produto entre estes 2 valores. Atribua esta operação a variável `PROD`, mostrando esta de acordo com a mensagem de saída esperada

Resposta: 

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
		Scanner leitor = new Scanner(System.in);
    
        int A, B, PROD;

        A = leitor.nextInt();
        B = leitor.nextInt();

        PROD = A * B ; //1° Adicionamos o operação de multiplicação de A por B

        System.out.printLn("prod = " + PROD); //Só adicionamos a variavel "PROD" após a string.

        leitor.close();

    }
}
```

### Desafio JS

Questão: 

Leia 2 valores inteiros identificados como variáveis A e B. Calcule a soma entre elas e chame essa variável de `SOMA`. A seguir, escreva o valor dessa variável.

```jsx
//Afunção "gets" é implementada dentro do sistema para ler as entradas (inputs) dos dados.
//A função "print" imprime a saida (output) de dados e já pula uma linha("\n").

let A = parseInt(gets());
let B = parseInt(gets());

let SOMA = A + B; //1° Atribui a operação de soma de A por B a variável soma.

print("Soma = " + SOMA);
```

---

### Areas úteis

- Central de ajuda → Dúvidas frequentes e/ou bugs.
- Artigos → Dicas, curiosidades e temas em alta.
- Rooms → Dúvidas técnicas relacionadas ao bootcamp.
- Live coding → Imersões  práticas avançadas (Geralmente as quartas feiras)