# Game.UI.InGame.ResourceSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Single <resourceAmount>k__BackingField;
    private Game.UI.InGame.ResourceSection+ResourceKey <resourceKey>k__BackingField;

    protected System.String group { protected get; }
    private System.Single resourceAmount { private get; private set; }
    private Game.UI.InGame.ResourceSection+ResourceKey resourceKey { private get; private set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }

    public ResourceSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private System.Single <resourceAmount>k__BackingField`  

```csharp
private System.Single <resourceAmount>k__BackingField;
```

- `private Game.UI.InGame.ResourceSection+ResourceKey <resourceKey>k__BackingField`  

```csharp
private Game.UI.InGame.ResourceSection+ResourceKey <resourceKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Single resourceAmount { private get; private set }`  

```csharp
private System.Single resourceAmount { private get; private set; }
```

- `private Game.UI.InGame.ResourceSection+ResourceKey resourceKey { private get; private set }`  

```csharp
private Game.UI.InGame.ResourceSection+ResourceKey resourceKey { private get; private set; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```


## Constructors

- `public ResourceSection()`  

```csharp
public ResourceSection();
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

- `Game.UI.InGame.ResourceSection+ResourceKey`  

