# Game.Prefabs.RandomGenderedLocalization

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RandomLocalization`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RandomGenderedLocalization : Game.Prefabs.RandomLocalization, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.String m_MaleID;
    public System.String m_FemaleID;

    public RandomGenderedLocalization();

    protected virtual System.Int32 GetLocalizationCount();
}
```


## Fields

- `public System.String m_MaleID`  

```csharp
public System.String m_MaleID;
```

- `public System.String m_FemaleID`  

```csharp
public System.String m_FemaleID;
```


## Constructors

- `public RandomGenderedLocalization()`  

```csharp
public RandomGenderedLocalization();
```


## Methods

- `protected virtual GetLocalizationCount() : System.Int32`  

```csharp
protected virtual System.Int32 GetLocalizationCount();
```


