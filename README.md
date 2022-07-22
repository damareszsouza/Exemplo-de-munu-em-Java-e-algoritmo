# Exemplo-de-munu-em-Java-e-algoritmo


 
Moodle - IFRS

Programação Básica com Java III - Turma 2022B
Painel Meus cursos  PBJIII2022B 1. Integrando Estruturas de Controle  1.5. Programas com Cardápios
1.5. Programas com Cardápios
Um componente importante da maioria dos programas atuais são os menus. Um menu em um restaurante contém o cardápio com todos os pratos disponíveis para escolha do cliente. No caso de um programa de computador, um menu contém uma lista de opções de ações que o usuário pode efetuar em um programa.

As ferramentas que aprendemos até aqui para construção de interfaces com o usuário ainda são bastante rudimentares, porém nos possibilitam criar menus simples de opções. Para visualizarmos como trabalhar com menus, vamos a um exemplo. Considere o enunciado abaixo:

Faça um programa que apresente o menu de opções a seguir, permita ao usuário escolher a opção desejada, receba os dados necessários para executar a operação e mostre o resultado. Verifique a possibilidade de opção inválida.

Menu de opções:

Imposto
Novo Salário
Classificação
Finalizar o programa
Na opção 1, receber o salário de um funcionário, calcular e mostrar o valor do imposto usando as seguintes regras:

Se o salário for menor do que R$ 1000,00, o percentual de imposto será de 5%.
Se o salário for um valor de R$ 1000,00 a R$ 3000,00, o percentual de imposto será de 10%.
Se o salário estiver acima de R$ 3000,00, o percentual de imposto será de 15%.
Na opção 2, receber o salário de um funcionário, calcular e mostrar o valor do novo salário usando as regras a seguir.

Para salários maiores do que R$ 4500,00, o aumento será de R$ 45,00.
Para salários de R$ 2250,00 até R$ 4500,00, o aumento será de R$ 150,00.
Para salários de R$ 1350,00 até R$ 2249,99, o aumento será de R$ 225,00.
Para salário menores que R$ 1350,00, o aumento será de R$ 300,00.
Na opção 3, receber o salário de um funcionário e mostrar sua classificação usando as seguintes regras:

Para salários até R$ 1500,00 a classificação será "Mal remunerado".
Para salários maiores que R$ 1500,00 a classificação será "Bem remunerado".
O programa que precisamos construir deve exibir o menu de opções enquanto o usuário não escolher a opção de finalizar o programa. O pseudocódigo abaixo mostra um algoritmo que repete a exibição do menu de opções enquanto o usuário não finalizar o programa. 




Algoritmo “Exemplo de menu”

var


opcao : inteiro


início

       repita

              escreva “Menu de opções:”

              escreva “1. Imposto”

              escreva “2. Novo salário”

              escreva “3. Classificação”

              escreva “4. Finalizar o programa”

              leia opcao


 


escolha opção


       caso 1: // Imposto


       caso 2: // Novo salário


       caso 3: // Classificação


       caso 4: escreva “Finalizando programa...”


       senão: escreva “Opção inválida”


fim escolha


       até que opção = 4

fim


As primeiras instruções escreva mostram o menu de opções na tela de saída. Note que utilizamos uma estrutura repita para o laço de repetição. Para esse tipo de repetição a estrutura repita se mostra mais adequada, por permitir um código menor e mais eficiente.

A opção escolhida pelo usuário ficará armazenada na variável opcao. Dependendo da opção escolhida, uma porção de código diferente deverá ser executada. Para realizar esse direcionamento, utilizamos uma estrutura escolha. Como vimos no capítulo 8, essa estrutura se mostra mais adequada quando precisamos efetuar repetidas comparações de uma mesma variável com valores diferentes. A parte senão do escolha foi utilizada para mostrar uma mensagem caso o usuário digite uma opção inválida (uma exigência de nosso enunciado).

A solução de cada subproblema para cada opção de menu deverá ser inserida em seu respectivo caso. As soluções para cada subproblema podem ser observadas no algoritmo abaixo.




Algoritmo “Exemplo de menu”

var


opcao : inteiro


       salario, imposto : real

início

       repita


escreva “Menu de opções:”


escreva “1. Imposto”


escreva “2. Novo salário”


escreva “3. Classificação”


escreva “4. Finalizar o programa”


leia opcao


 


escolha opcao


       caso 1:


             leia salario


             se salario < 1000 então


                    imposto ← salario * 0.05


             senão


                    se salario <= 3000 então


                           imposto ← salario * 0.10


                    senão


                           imposto ← salario * 0.15


                    fim se


             fim se


             escreva imposto


       caso 2:


             leia salario


             se salario < 1350 então


                    salario ← salario + 300


             senão


                    se salario < 2250 então


                           salario ← salario + 225


                    senão


                           se salario <= 4500 então


                                  salario ← salario + 150


                           senão


                                  salario ← salario + 75


                           fim se


                    fim se


             fim se


             escreva salario


       caso 3:


             leia salario


             se salario <= 1500 então


                    escreva “Mal remunerado”


             senão


                    escreva “Bem remunerado”


             fim se


       caso 4: escreva “Finalizando programa...”


       senão: escreva “Opção inválida”


fim escolha



       até que opção = 4

fim

public class ExemploMenu {


public static void main(String[] args) {


int opcao;


double salario, imposto;


              do {


System.out.println(“Menu de opções:”);


                     System.out.println(“1. Imposto”);

                     System.out.println(“2. Novo salário”);

                     System.out.println(“3. Classificação”);

                     System.out.println(“4. Finalizar o programa”);


System.out.print(“Digite sua opção: ”);


opcao = Integer.parseInt(System.console().readLine());


 


switch(opcao) {


                           case 1:

                                  System.out.print(“Salário do funcionário: ”);


                    salario = Double.parseDouble(System.console().readLine());


                    if(salario < 1000)

                           imposto = salario * 0.05;

                    else if(salario <= 3000)

                           imposto = salario * 0.10;

                    else

                           imposto = salario * 0.15;

                                  System.out.printf(“Imposto = R$ %.2f\n”, imposto);

                                  break;

                           case 2:

                                  System.out.print(“Salário do funcionário: ”);

                    salario = Double.parseDouble(System.console().readLine());

                    if(salario < 1350)

                           salario += 300;

                    else if(salario < 2250)

                           salario += 225;

                    else if(salario <= 4500)

                           salario += 150;

                    else

                           salario += 75;

                    System.out.printf(“Novo Salário = R$ %.2f\n“, salario);

                                  break;

                           case 3:

                                  System.out.print(“Salário do funcionário: ”);

                    salario = Double.parseDouble(System.console().readLine());

                    if(salario <= 1500)

                           System.out.println(“Mal remunerado”);

                    else

                           System.out.println(“Bem remunerado”);


                                  break;

                           case 4: System.out.println(“Finalizando programa...”); break;

                           default: System.out.println(“Opção inválida!”); break;

                    }

          } while(opcao != 4);

    }

}
