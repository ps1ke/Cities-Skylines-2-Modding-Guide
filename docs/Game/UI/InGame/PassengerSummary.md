# Game.UI.InGame.TransportInfoviewUISystem+PassengerSummary

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct PassengerSummary
{
    private readonly Unity.Entities.Entity m_Prefab;
    private readonly System.String <id>k__BackingField;
    private readonly System.String <icon>k__BackingField;
    private readonly System.Boolean <locked>k__BackingField;
    private readonly System.Int32 <lineCount>k__BackingField;
    private readonly System.Int32 <touristCount>k__BackingField;
    private readonly System.Int32 <citizenCount>k__BackingField;

    public System.String id { get; }
    public System.String icon { get; }
    public System.Boolean locked { get; }
    public System.Int32 lineCount { get; }
    public System.Int32 touristCount { get; }
    public System.Int32 citizenCount { get; }

    public PassengerSummary(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked, System.Int32 lineCount, System.Int32 touristCount, System.Int32 citizenCount);

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

- `private readonly System.Int32 <touristCount>k__BackingField`  

```csharp
private readonly System.Int32 <touristCount>k__BackingField;
```

- `private readonly System.Int32 <citizenCount>k__BackingField`  

```csharp
private readonly System.Int32 <citizenCount>k__BackingField;
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

- `public System.Int32 touristCount { get }`  

```csharp
public System.Int32 touristCount { get; }
```

- `public System.Int32 citizenCount { get }`  

```csharp
public System.Int32 citizenCount { get; }
```


## Constructors

- `public PassengerSummary(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked, System.Int32 lineCount, System.Int32 touristCount, System.Int32 citizenCount)`  

```csharp
public PassengerSummary(Unity.Entities.Entity prefab, System.String id, System.String icon, System.Boolean locked, System.Int32 lineCount, System.Int32 touristCount, System.Int32 citizenCount);
```


## Methods

- `public Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Game.UI.InGame.PrefabUISystem prefabUISystem, Colossal.UI.Binding.IJsonWriter writer);
```


