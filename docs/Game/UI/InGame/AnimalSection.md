# Game.UI.InGame.AnimalSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimalSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.AnimalSection+TypeKey <typeKey>k__BackingField;
    private Unity.Entities.Entity <ownerEntity>k__BackingField;
    private Unity.Entities.Entity <destinationEntity>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.AnimalSection+TypeKey typeKey { private get; private set; }
    private Unity.Entities.Entity ownerEntity { private get; private set; }
    private Unity.Entities.Entity destinationEntity { private get; private set; }

    public AnimalSection();

    private Unity.Entities.Entity GetDestination();
    private Game.UI.InGame.AnimalSection+TypeKey GetTypeKey();
    private System.String GetTypeKeyString(Game.UI.InGame.AnimalSection+TypeKey typeKey);
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.AnimalSection+TypeKey <typeKey>k__BackingField`  

```csharp
private Game.UI.InGame.AnimalSection+TypeKey <typeKey>k__BackingField;
```

- `private Unity.Entities.Entity <ownerEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <ownerEntity>k__BackingField;
```

- `private Unity.Entities.Entity <destinationEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <destinationEntity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.AnimalSection+TypeKey typeKey { private get; private set }`  

```csharp
private Game.UI.InGame.AnimalSection+TypeKey typeKey { private get; private set; }
```

- `private Unity.Entities.Entity ownerEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity ownerEntity { private get; private set; }
```

- `private Unity.Entities.Entity destinationEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity destinationEntity { private get; private set; }
```


## Constructors

- `public AnimalSection()`  

```csharp
public AnimalSection();
```


## Methods

- `private GetDestination() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetDestination();
```

- `private GetTypeKey() : Game.UI.InGame.AnimalSection+TypeKey`  

```csharp
private Game.UI.InGame.AnimalSection+TypeKey GetTypeKey();
```

- `private GetTypeKeyString(Game.UI.InGame.AnimalSection+TypeKey typeKey) : System.String`  

```csharp
private System.String GetTypeKeyString(Game.UI.InGame.AnimalSection+TypeKey typeKey);
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


## Nested types

- `Game.UI.InGame.AnimalSection+TypeKey`  

