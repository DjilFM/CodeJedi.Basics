# Programmation orientée objet en C\#

## Introduction

Le langage c\# permet de couvrir tous les concepts de la programation orientée objet.
Dans ce chapitre nous allons aborder tous ces concepts ainsi que les spécifictés du C\# 7.

## Class et Structs

Les classes et structures sont deux des constructions de base en langage C#. Chacune est une structure de données qui encapsule un ensemble de données et de comportements . Les données et comportements forment les membres de la classe ou de la structure, cela inclue les méthodes, les propriétés, les champs, les évenement etc..

### Class

Les classes ont pour but de décrire un type d'objet, alors que l'objet est une instance de classe, c'est pour celà que la creation d'objet est appelé instance de classe.
Si on veut faire l'anolgie de ce concept la classe sera un moule pour une pièce industruelle, et l'objet correspondra à la pièce crée à partir du moule :).

#### Exemple

```c#
public class BankAccount
{
    // Class members.
    // Property.
    public string FirstName { get; set; }

    public string LastName { get; set; }

    public decimal Balance { get; set;}
    // Instance Constructor.
    public BankAccount(string firstName, string lastName, decimal balance)
    {
        FirstName = firstName;
        LastName = lastName;
        Balance = balance;
    }
    // Method.
    public MakeDeposit(decimal ammount)
    {
        Balance+=amount;
    }
    public MakeWithdrawal(decimal ammount)
    {
        Balance-=amount;
    }
}
```