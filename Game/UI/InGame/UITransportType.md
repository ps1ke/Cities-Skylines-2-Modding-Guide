# Game.UI.InGame.UITransportType

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct UITransportType
{
    private readonly Unity.Entities.Entity m_Prefab;
    private readonly System.String <id>k__BackingField;
    private readonly System.String <icon>k__BackingField;
    private readonly System.Boolean <locked>k__BackingField;

    public System.String id { get; }
    public System.String icon { get; }
    public System.Boolean locked { get; }

    public UITransportType(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked);

    public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly Unity.Entities.Entity m_Prefab`  

```csharp
private readonly Unity.Entities.Entity m_Prefab;
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


## Properties

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


## Constructors

- `public UITransportType(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked)`  

```csharp
public UITransportType(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked);
```


## Methods

- `public Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
```


