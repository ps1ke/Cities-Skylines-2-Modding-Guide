# Game.UI.InGame.TitleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TitleSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.ImageSystem m_ImageSystem;
    private System.String <icon>k__BackingField;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private System.String icon { private get; private set; }

    public TitleSection();

    public static System.String GetVirtualKeyboardLocaleKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnProcess();
    private System.Void OnRename(System.String newName);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private System.String <icon>k__BackingField`  

```csharp
private System.String <icon>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
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

- `private System.String icon { private get; private set }`  

```csharp
private System.String icon { private get; private set; }
```


## Constructors

- `public TitleSection()`  

```csharp
public TitleSection();
```


## Methods

- `public static GetVirtualKeyboardLocaleKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  

```csharp
public static System.String GetVirtualKeyboardLocaleKey(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `private OnRename(System.String newName) : System.Void`  

```csharp
private System.Void OnRename(System.String newName);
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


