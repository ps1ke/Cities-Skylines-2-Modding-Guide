# Game.UI.InGame.TransportInfoviewUISystem+CargoSummary

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct CargoSummary
{
    private readonly Unity.Entities.Entity m_Prefab;
    private readonly System.String <id>k__BackingField;
    private readonly System.String <icon>k__BackingField;
    private readonly System.Boolean <locked>k__BackingField;
    private readonly System.Int32 <lineCount>k__BackingField;
    private readonly System.Int32 <cargoCount>k__BackingField;

    public System.String id { get; }
    public System.String icon { get; }
    public System.Boolean locked { get; }
    public System.Int32 lineCount { get; }
    public System.Int32 cargoCount { get; }

    public CargoSummary(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked, System.Int32 lineCount, System.Int32 cargoCount);

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

- `private readonly System.Int32 <lineCount>k__BackingField`  

```csharp
private readonly System.Int32 <lineCount>k__BackingField;
```

- `private readonly System.Int32 <cargoCount>k__BackingField`  

```csharp
private readonly System.Int32 <cargoCount>k__BackingField;
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

- `public System.Int32 lineCount { get }`  

```csharp
public System.Int32 lineCount { get; }
```

- `public System.Int32 cargoCount { get }`  

```csharp
public System.Int32 cargoCount { get; }
```


## Constructors

- `public CargoSummary(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked, System.Int32 lineCount, System.Int32 cargoCount)`  

```csharp
public CargoSummary(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked, System.Int32 lineCount, System.Int32 cargoCount);
```


## Methods

- `public Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
```


