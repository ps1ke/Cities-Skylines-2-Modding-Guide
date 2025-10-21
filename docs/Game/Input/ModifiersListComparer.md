# Game.Input.ProxyBinding+ModifiersListComparer

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEqualityComparer<System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier>>`  

## Code

```csharp
public class ModifiersListComparer : System.Collections.Generic.IEqualityComparer<System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier>>
{
    private readonly Game.Input.ProxyModifier+Comparer m_ModifierComparer;
    public static readonly Game.Input.ProxyBinding+ModifiersListComparer defaultComparer;

    public ModifiersListComparer(Game.Input.ProxyModifier+Comparer modifierComparer);

    public System.Boolean Equals(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> x, System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> y);
    public System.Int32 GetHashCode(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> list);
}
```


## Fields

- `private readonly Game.Input.ProxyModifier+Comparer m_ModifierComparer`  

```csharp
private readonly Game.Input.ProxyModifier+Comparer m_ModifierComparer;
```

- `public static readonly Game.Input.ProxyBinding+ModifiersListComparer defaultComparer`  

```csharp
public static readonly Game.Input.ProxyBinding+ModifiersListComparer defaultComparer;
```


## Constructors

- `public ModifiersListComparer(Game.Input.ProxyModifier+Comparer modifierComparer = null)`  

```csharp
public ModifiersListComparer(Game.Input.ProxyModifier+Comparer modifierComparer);
```


## Methods

- `public Equals(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> x, System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> y) : System.Boolean`  

```csharp
public System.Boolean Equals(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> x, System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> y);
```

- `public GetHashCode(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> list) : System.Int32`  

```csharp
public System.Int32 GetHashCode(System.Collections.Generic.IReadOnlyCollection<Game.Input.ProxyModifier> list);
```


