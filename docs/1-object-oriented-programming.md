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
    public double Latitude { get; }
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
> * On ne peux pas redéfinir un constructeur par défaut (sans paramètres) dans un `struct`.
> * La valeur par défaut d'un `struct` ne peux pas ètre `null` contrairement à une `class`.
> * `default(Type)` et `new Type()` renvoient la valeur par défaut de la structure, où tous les champs ont leur valeur par défaut.
> * Il n'exite pas d'héritage pour un `struct`.
> * Un `struct` est de type valeur contrairement à `class` qui est de type référence.

### Membres

Une `class` peut avoir plusieurs membres, ces membres permettent de définir le comportement de la classe.

#### Champs

Les champs sont similaires aux variables, car ils peuvent être lus ou définis directement.
Exemple pour définir un champ:

```c#
class SampleClass  
{  
    private string _sampleField;  
}  
```

En règle générale, vous devez utiliser des champs uniquement pour les variables dont l’accessibilité est **privée** ou **protégée**.

#### Propriétés

Une propriété est un membre qui fournit un mécanisme flexible pour la lecture, l'écriture ou le calcul de la valeur d'un champ privé.

Exemple:

```c#
class SampleClass  
{  
    private string _sampleProperty;
    public string SampleProperty
    {
        get
        {
            return _sampleProperty;
        }
        set
        {
            _sampleProperty = value;
        }
    }
}  
```

C# vous permet d’utiliser des propriétés implémentées automatiquement.

Exemple:

```c#
class SampleClass  
{  
    public string SampleProperty { get; set; }
}  
```

Voici le code réel correspendant:

```c#
internal class SampleClass
{
    private string _sampleProperty;

    [CompilerGenerated]
    [DebuggerBrowsable(DebuggerBrowsableState.Never)]
    private string <SampleProperty>k__BackingField;

    public string SampleProperty
    {
        [CompilerGenerated]
        get
        {
            return <SampleProperty>k__BackingField;
        }
        [CompilerGenerated]
        set
        {
            <SampleProperty>k__BackingField = value;
        }
    }
}

```

On remarque que le code réel généré pour cet exemple correspond au premier exemple.

>Astuce pour avoir le code réel : <https://sharplab.io/>

#### Méthodes

Une méthode correspond à une action qu’un objet peut effectuer.

```c#
class TestClass  
{  
    public int TestMethod(string sampleParam)  
    {  
        // Insert code here  
    }  
}  
```

Dans la plupart des cas, on déclare une méthode dans une classe. Toutefois, C# prend charge les [méthodes d’extension]( https://docs.microsoft.com/fr-fr/dotnet/csharp/programming-guide/classes-and-structs/extension-methods), qui permettent d’ajouter des méthodes à une classe existante hors de la définition réelle de la classe.

#### Événements

Les événements permettent à une classe ou un objet de notifier d'autres classes. La classe déclenche appelée `Publishers` et les classes qui gèrent l’événement sont appelées `Subscribers`. Pour plus d’informations sur les événements, leur déclenchement et leur gestion, consultez [Événements](https://docs.microsoft.com/fr-fr/dotnet/standard/events/index).

#### Modificateurs d’accèssibilité

Toute les classe ainsi que ces membres peuvent spécifier le niveau d'accés qu'ils fournissent, voici un tableau résumant les différents niveaux d'accés:
