# Desafio 1:  Dividindo X por Y

Você terá o desafio de escrever um algoritmo que leia 2 números e imprima o resultado da divisão do primeiro pelo segundo. Caso não for possível mostre a mensagem “divisao impossivel” para os valores em questão.

## Entrada

A entrada contém um número inteiro **N**. Este **N** será a quantidade de pares de valores inteiros (X e Y) que serão lidos em seguida.

## Saída

Para cada caso mostre o resultado da divisão com um dígito após o ponto decimal, ou “divisao impossivel” caso não seja possível efetuar o cálculo.



| Exemplo de Entrada | Saída              |
| ------------------ | ------------------ |
| 4                  |                    |
| 3 -2               | -1.5               |
| -8 0               | divisao impossivel |
| 0 8                | 0.0                |
| 1 -20              | -0.0               |

**Resolução:**

```
using System;

class Desafio 
{
  static void Main(string[] args) 
  {
     int limit = Int32.Parse(Console.ReadLine());
      for (int i = 0; i < limit; i++)
      {
        string[] line = Console.ReadLine().Split(" ");
        
        double X = double.Parse(line[0]);
        double Y = double.Parse(line[1]);
        
        if (Y == 0)
        {
          Console.WriteLine("divisao impossivel");
        }
        else
        {
          double divisao = (double)X / Y;
                    
          if(divisao < 0 && divisao > -0.5)
          {
            Console.WriteLine("-0.0");
          }
          else
          {
            Console.WriteLine(divisao.ToString("N1"));
          }
      }
    }
  }
}
```



# Desafio 4: Quadrado e ao Cubo

Você terá o desafio de escrever um programa que leia um valor inteiro N (1 < N < 1000). Este N é a quantidade de linhas de saída que serão apresentadas na execução do programa.

## Entrada

O arquivo de entrada contém um número inteiro positivo N.

## Saída

Imprima a saída conforme o exemplo fornecido.



| Exemplo de Entrada | Exemplo de Saída |
| ------------------ | ---------------- |
| 5                  | 1 1 1            |
|                    | 2 4 8            |
|                    | 3 9 27           |
|                    | 4 16 64          |
|                    | 5 25 125         |



**Resolução:**

```
using System;

class Desafio 
{
  static void Main(string[] args) 
  {
   int limit = Int32.Parse(Console.ReadLine());
   string num1, num2, num3;

    if (limit >= 1 && limit < 1000) //intervalo entre 1 e 999
    {
     for (int x = 1; x <= limit; x++)
      {
        num1 = Math.Pow(x, 1).ToString();
        num2 = Math.Pow(x, 2).ToString();
        num3 = Math.Pow(x, 3).ToString();

        Console.WriteLine($"{num1} {num2} {num3}");
      }
    }
  }
}
```



# Desafio 5: A Corrida de Tartarugas

A corrida de tartarugas é um esporte que cresceu muito nos últimos anos, fazendo com que vários competidores se dediquem a capturar tartarugas rápidas, e treina-las para faturar milhões em corridas pelo mundo. Porém a tarefa de capturar tartarugas não é uma tarefa muito fácil, pois quase todos esses répteis são bem lentos. Cada tartaruga é classificada em um nível dependendo de sua velocidade:


Nível 1: Se a velocidade é menor que 10 cm/h .
Nível 2: Se a velocidade é maior ou igual a 10 cm/h e menor que 20 cm/h .
Nível 3: Se a velocidade é maior ou igual a 20 cm/h .

Sua tarefa é identificar qual o nível de velocidade da tartaruga mais veloz de um grupo.



## Entrada

A entrada consiste de múltiplos casos de teste, e cada um consiste em duas linhas: A primeira linha contém um inteiro **L** (1 ≤ **L** ≤ 500) representando o número de tartarugas do grupo, e a segunda linha contém **L** inteiros **Vi** (1 ≤ **Vi** ≤ 50) representando as velocidades de cada tartaruga do grupo.



## Saída

Para cada caso de teste, imprima uma única linha indicando o nível de velocidade da tartaruga mais veloz do grupo.



| Exemplo de Entrada            | Exemplo de Saída |
| ----------------------------- | ---------------- |
| 10                            |                  |
| 10 10 10 10 15 18 20 15 11 10 | 3                |
| 10                            |                  |
| 1 5 2 9 5 5 8 4 4 3           | 1                |
| 10                            |                  |
| 19 9 1 4 5 8 6 11 9 7         | 2                |

**Resolução:**

```
using System;

class Desafio 
{
  static void Main(string[] args) 
  {
     int qtyTurtle;
     bool IsValid = true;

    while (IsValid)
    {
        if (!(Int32.TryParse(Console.ReadLine(), out qtyTurtle)))
         {
           IsValid = false;
           break;
         }

      if (qtyTurtle >= 1 && qtyTurtle <= 500)
        {
          string[] aux = new string[qtyTurtle];

          aux = Console.ReadLine().Split(" ");

          int[] line = new int[qtyTurtle];

          int fast = 0;

        for (int i = 0; i < qtyTurtle; i++)
        {
            line[i] = Int32.Parse(aux[i]);

          if (!(line[i] >= 1 && line[i] <= 50))
          {
             IsValid = false;
             break;
          } 

          if (line[i] > fast) fast = line[i];
        }

      if (IsValid)
      {
         if (fast < 10)
          {
          	Console.WriteLine(1);
          }
          else if (fast >= 10 && fast < 20)
          {
          	Console.WriteLine(2);
          }
          else
          {
            Console.WriteLine(3);
          }
        }
      }
      else
      {
        IsValid = false;
      }
    }
  }
}
```

