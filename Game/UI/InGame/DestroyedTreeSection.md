# Game.UI.InGame.DestroyedTreeSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DestroyedTreeSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <destroyer>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity destroyer { private get; private set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }

    public DestroyedTreeSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity <destroyer>k__BackingField`  

```csharp
private Unity.Entities.Entity <destroyer>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Entities.Entity destroyer { private get; private set }`  

```csharp
private Unity.Entities.Entity destroyer { private get; private set; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```


## Constructors

- `public DestroyedTreeSection()`  

```csharp
public DestroyedTreeSection();
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


