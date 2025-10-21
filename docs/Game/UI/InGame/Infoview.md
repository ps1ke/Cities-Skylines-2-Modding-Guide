# Game.UI.InGame.InfoviewsUISystem+Infoview

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.InfoviewsUISystem+Infoview>`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct Infoview : System.IComparable<Game.UI.InGame.InfoviewsUISystem+Infoview>
{
    private readonly Unity.Entities.Entity <entity>k__BackingField;
    private readonly System.String <id>k__BackingField;
    private readonly System.String <icon>k__BackingField;
    private readonly System.Boolean <locked>k__BackingField;
    private readonly System.String <uiTag>k__BackingField;
    private readonly System.Int32 <group>k__BackingField;
    private readonly System.Int32 <priority>k__BackingField;
    private readonly System.Boolean <editor>k__BackingField;

    public Unity.Entities.Entity entity { get; }
    public System.String id { get; }
    public System.String icon { get; }
    public System.Boolean locked { get; }
    public System.String uiTag { get; }
    public System.Int32 group { get; }
    private System.Int32 priority { private get; }
    private System.Boolean editor { private get; }

    public Infoview(Unity.Entities.Entity entity, Game.Prefabs.InfoviewPrefab prefab, System.Boolean locked);

    public System.Int32 CompareTo(Game.UI.InGame.InfoviewsUISystem+Infoview other);
    public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <entity>k__BackingField;
```

- `private readonly System.String <id>k__BackingField`  

```csharp
private readonly System.String <id>k__BackingField;
```

- `private readonly System.String <icon>k__BackingField`  

```csharp
private readonly System.String <icon>k__BackingField;
```

- `private readonly System.Boolean <locked>k__BackingField`  

```csharp
private readonly System.Boolean <locked>k__BackingField;
```

- `private readonly System.String <uiTag>k__BackingField`  

```csharp
private readonly System.String <uiTag>k__BackingField;
```

- `private readonly System.Int32 <group>k__BackingField`  

```csharp
private readonly System.Int32 <group>k__BackingField;
```

- `private readonly System.Int32 <priority>k__BackingField`  

```csharp
private readonly System.Int32 <priority>k__BackingField;
```

- `private readonly System.Boolean <editor>k__BackingField`  

```csharp
private readonly System.Boolean <editor>k__BackingField;
```


## Properties

- `public Unity.Entities.Entity entity { get }`  

```csharp
public Unity.Entities.Entity entity { get; }
```

- `public System.String id { get }`  

```csharp
public System.String id { get; }
```

- `public System.String icon { get }`  

```csharp
public System.String icon { get; }
```

- `public System.Boolean locked { get }`  

```csharp
public System.Boolean locked { get; }
```

- `public System.String uiTag { get }`  

```csharp
public System.String uiTag { get; }
```

- `public System.Int32 group { get }`  

```csharp
public System.Int32 group { get; }
```

- `private System.Int32 priority { private get }`  

```csharp
private System.Int32 priority { private get; }
```

- `private System.Boolean editor { private get }`  

```csharp
private System.Boolean editor { private get; }
```


## Constructors

- `public Infoview(Unity.Entities.Entity entity, Game.Prefabs.InfoviewPrefab prefab, System.Boolean locked)`  

```csharp
public Infoview(Unity.Entities.Entity entity, Game.Prefabs.InfoviewPrefab prefab, System.Boolean locked);
```


## Methods

- `public CompareTo(Game.UI.InGame.InfoviewsUISystem+Infoview other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.InfoviewsUISystem+Infoview other);
```

- `public Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
```


