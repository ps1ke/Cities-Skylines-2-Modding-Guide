# Game.Buildings.LocalEffectSystem+EffectItem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Buildings.LocalEffectSystem+EffectItem>`  

## Code

```csharp
public sealed struct EffectItem : System.IEquatable<Game.Buildings.LocalEffectSystem+EffectItem>
{
    public Unity.Entities.Entity m_Provider;
    public Game.Buildings.LocalModifierType m_Type;

    public EffectItem(Unity.Entities.Entity provider, Game.Buildings.LocalModifierType type);

    public System.Boolean Equals(Game.Buildings.LocalEffectSystem+EffectItem other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Provider`  

```csharp
public Unity.Entities.Entity m_Provider;
```

- `public Game.Buildings.LocalModifierType m_Type`  

```csharp
public Game.Buildings.LocalModifierType m_Type;
```


## Constructors

- `public EffectItem(Unity.Entities.Entity provider, Game.Buildings.LocalModifierType type)`  

```csharp
public EffectItem(Unity.Entities.Entity provider, Game.Buildings.LocalModifierType type);
```


## Methods

- `public Equals(Game.Buildings.LocalEffectSystem+EffectItem other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Buildings.LocalEffectSystem+EffectItem other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


