# Game.UI.InGame.LoadSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class LoadSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <load>k__BackingField;
    private System.Single <capacity>k__BackingField;
    private Game.UI.InGame.LoadSection+LoadKey <loadKey>k__BackingField;

    protected System.String group { protected get; }
    private System.Single load { private get; private set; }
    private System.Single capacity { private get; private set; }
    private Game.UI.InGame.LoadSection+LoadKey loadKey { private get; private set; }
    protected Unity.Entities.Entity selectedEntity { protected get; }
    protected Unity.Entities.Entity selectedPrefab { protected get; }

    public LoadSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Single <load>k__BackingField`  

```csharp
private System.Single <load>k__BackingField;
```

- `private System.Single <capacity>k__BackingField`  

```csharp
private System.Single <capacity>k__BackingField;
```

- `private Game.UI.InGame.LoadSection+LoadKey <loadKey>k__BackingField`  

```csharp
private Game.UI.InGame.LoadSection+LoadKey <loadKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single load { private get; private set }`  

```csharp
private System.Single load { private get; private set; }
```

- `private System.Single capacity { private get; private set }`  

```csharp
private System.Single capacity { private get; private set; }
```

- `private Game.UI.InGame.LoadSection+LoadKey loadKey { private get; private set }`  

```csharp
private Game.UI.InGame.LoadSection+LoadKey loadKey { private get; private set; }
```

- `protected Unity.Entities.Entity selectedEntity { protected get }`  

```csharp
protected Unity.Entities.Entity selectedEntity { protected get; }
```

- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

```csharp
protected Unity.Entities.Entity selectedPrefab { protected get; }
```


## Constructors

- `public LoadSection()`  

```csharp
public LoadSection();
```


## Methods

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


## Nested types

- `Game.UI.InGame.LoadSection+LoadKey`  

