# Game.UI.InGame.DummyHumanSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class DummyHumanSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <originEntity>k__BackingField;
    private Unity.Entities.Entity <destinationEntity>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity originEntity { private get; private set; }
    private Unity.Entities.Entity destinationEntity { private get; private set; }

    public DummyHumanSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity <originEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <originEntity>k__BackingField;
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

- `private Unity.Entities.Entity originEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity originEntity { private get; private set; }
```

- `private Unity.Entities.Entity destinationEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity destinationEntity { private get; private set; }
```


## Constructors

- `public DummyHumanSection()`  

```csharp
public DummyHumanSection();
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

- `private Visible() : System.Boolean`  

```csharp
private System.Boolean Visible();
```


