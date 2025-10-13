# Game.Input.IDisableableProcessor

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDisableableProcessor
{
    public static const System.Boolean kDefaultCanBeDisabled;

    public System.Boolean canBeDisabled { get; }
    public System.Boolean disabled { get; set; }

}
```


## Fields

- `public static const System.Boolean kDefaultCanBeDisabled`  

```csharp
public static const System.Boolean kDefaultCanBeDisabled;
```


## Properties

- `public System.Boolean canBeDisabled { get }`  

```csharp
public System.Boolean canBeDisabled { get; }
```

- `public System.Boolean disabled { get; set }`  

```csharp
public System.Boolean disabled { get; set; }
```


