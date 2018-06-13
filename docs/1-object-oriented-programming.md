# Programmation orientée objet en C\#

## Introduction

Le langage c\# permet de couvrir tous les concepts de la programation orientée objet.
Dans ce chapitre nous allons aborder tous ces concepts ainsi que les spécifictés du C\# 7.

## Class et Structs

Les classes et structures sont deux des constructions de base en langage C#. Chacune est une structure de données qui encapsule un ensemble de données et de comportements . Les données et comportements forment les membres de la classe ou de la structure, cela inclue les méthodes, les propriétés, les champs, les évenement etc..

### Class

Les classes ont pour but de décrire un type d'objet, alors que l'objet est une instance de classe, c'est pour celà que la creation d'objet est appelé instance de classe.
Si on veut faire l'anologie de ce concept la classe sera un moule pour une pièce industruelle, et l'objet correspondra à la pièce crée à partir du moule.

#### Exemple 1

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
    public MakeDeposit(decimal amount)
    {
        Balance += amount;
    }
    public MakeWithdrawal(decimal ammount)
    {
        Balance -= amount;
    }
}
```

### Struct

Le type `struct` est approprié pour représenter des objets légers tels que Point, Rectangle et Couleur.
Un `struct` peut être plus efficace dans certains scénarios. Par exemple, si on déclare un tableau de 100 objets `Coordinates`, vous devez allouer de la mémoire supplémentaire pour faire référence à chacun des objets. Dans ce cas, un struct est moins couteux.

#### Exemple 2

```c#
public struct Coordinates
{
    public double Latitude { get; set; }
    public double Longitude { get; }
    public Coordinates(double latitude, double longitude)
    {
        Latitude = latitude;
        Longitude = longitude;
    }
}
```

>#### Spécificités des structures
>
> * On ne peux pas définir un constructeur par défaut (sans paramètres) dans une `struct`.
> * La valeur par défaut d'une `struct` ne peux pas ètre `null` contrairement à une `class`.
> * Les membres d'une valeur par défaut d'une `struct` sont affécté en fonction de leur valeurs par défaut.
> * Il n'exite pas d'héritage pour une `struct`.
> * `struct` sont de type valeur contrairement à `class` qui est de type référence.