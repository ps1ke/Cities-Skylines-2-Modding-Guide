# Game.UI.InGame.DeveloperSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.InGame.ISubsectionProvider`  

## Code

```csharp
public class DeveloperSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable, Game.UI.InGame.ISubsectionProvider
{
    private System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> <subsections>k__BackingField;

    protected System.String group { protected get; }
    public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; private set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }

    public DeveloperSection();

    public System.Void AddSubsection(Game.UI.InGame.ISubsectionSource subsection);
    private System.Int32 GetSubsectionCount();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> <subsections>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> <subsections>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; private set }`  

```csharp
public System.Collections.Generic.List<Game.UI.InGame.ISubsectionSource> subsections { get; private set; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```


## Constructors

- `public DeveloperSection()`  

```csharp
public DeveloperSection();
```


## Methods

- `public AddSubsection(Game.UI.InGame.ISubsectionSource subsection) : System.Void`  

```csharp
public System.Void AddSubsection(Game.UI.InGame.ISubsectionSource subsection);
```

- `private GetSubsectionCount() : System.Int32`  

```csharp
private System.Int32 GetSubsectionCount();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
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


