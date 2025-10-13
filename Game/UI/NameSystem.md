# Game.UI.NameSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NameSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_Names;

    public NameSystem();

    public System.Void BindFamilyName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity household);
    public System.Void BindName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    public System.Void BindNameForVirtualKeyboard(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
    public System.Void Deserialize<TReader>(TReader reader);
    private System.String GetBrandId(Unity.Entities.Entity building);
    private Game.UI.NameSystem+Name GetCitizenName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    public System.String GetDebugName(Unity.Entities.Entity entity);
    private Game.UI.NameSystem+Name GetFamilyName(Unity.Entities.Entity household);
    private System.String GetGenderedLastNameId(Unity.Entities.Entity household, System.Boolean male);
    private System.String GetId(Unity.Entities.Entity entity, System.Boolean useRandomLocalization);
    private Game.UI.NameSystem+Name GetMarkerTransportStopName(Unity.Entities.Entity stop);
    public Game.UI.NameSystem+Name GetName(Unity.Entities.Entity entity, System.Boolean omitBrand);
    public Game.UI.NameSystem+Name GetNameForVirtualKeyboard(Unity.Entities.Entity entity);
    public System.String GetRenderedLabelName(Unity.Entities.Entity entity);
    private Game.UI.NameSystem+Name GetResidentName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    private Game.UI.NameSystem+Name GetRouteName(Unity.Entities.Entity route, Unity.Entities.Entity prefab);
    private Game.UI.NameSystem+Name GetSpawnableBuildingName(Unity.Entities.Entity building, Unity.Entities.Entity zone, System.Boolean omitBrand);
    private Game.UI.NameSystem+Name GetStaticTransportStopName(Unity.Entities.Entity stop);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetCustomName(Unity.Entities.Entity entity, System.String name);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Boolean TryGetCustomName(Unity.Entities.Entity entity, System.String& customName);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_Names`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_Names;
```


## Constructors

- `public NameSystem()`  

```csharp
public NameSystem();
```


## Methods

- `public BindFamilyName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity household) : System.Void`  

```csharp
public System.Void BindFamilyName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity household);
```

- `public BindName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void BindName(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `public BindNameForVirtualKeyboard(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void BindNameForVirtualKeyboard(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private GetBrandId(Unity.Entities.Entity building) : System.String`  

```csharp
private System.String GetBrandId(Unity.Entities.Entity building);
```

- `private GetCitizenName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  

```csharp
private Game.UI.NameSystem+Name GetCitizenName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `public GetDebugName(Unity.Entities.Entity entity) : System.String`  

```csharp
public System.String GetDebugName(Unity.Entities.Entity entity);
```

- `private GetFamilyName(Unity.Entities.Entity household) : Game.UI.NameSystem+Name`  

```csharp
private Game.UI.NameSystem+Name GetFamilyName(Unity.Entities.Entity household);
```

- `private GetGenderedLastNameId(Unity.Entities.Entity household, System.Boolean male) : System.String`  

```csharp
private System.String GetGenderedLastNameId(Unity.Entities.Entity household, System.Boolean male);
```

- `private GetId(Unity.Entities.Entity entity, System.Boolean useRandomLocalization = True) : System.String`  

```csharp
private System.String GetId(Unity.Entities.Entity entity, System.Boolean useRandomLocalization);
```

- `private GetMarkerTransportStopName(Unity.Entities.Entity stop) : Game.UI.NameSystem+Name`  

```csharp
private Game.UI.NameSystem+Name GetMarkerTransportStopName(Unity.Entities.Entity stop);
```

- `public GetName(Unity.Entities.Entity entity, System.Boolean omitBrand = False) : Game.UI.NameSystem+Name`  

```csharp
public Game.UI.NameSystem+Name GetName(Unity.Entities.Entity entity, System.Boolean omitBrand);
```

- `public GetNameForVirtualKeyboard(Unity.Entities.Entity entity) : Game.UI.NameSystem+Name`  

```csharp
public Game.UI.NameSystem+Name GetNameForVirtualKeyboard(Unity.Entities.Entity entity);
```

- `public GetRenderedLabelName(Unity.Entities.Entity entity) : System.String`  

```csharp
public System.String GetRenderedLabelName(Unity.Entities.Entity entity);
```

- `private GetResidentName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  

```csharp
private Game.UI.NameSystem+Name GetResidentName(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `private GetRouteName(Unity.Entities.Entity route, Unity.Entities.Entity prefab) : Game.UI.NameSystem+Name`  

```csharp
private Game.UI.NameSystem+Name GetRouteName(Unity.Entities.Entity route, Unity.Entities.Entity prefab);
```

- `private GetSpawnableBuildingName(Unity.Entities.Entity building, Unity.Entities.Entity zone, System.Boolean omitBrand = False) : Game.UI.NameSystem+Name`  

```csharp
private Game.UI.NameSystem+Name GetSpawnableBuildingName(Unity.Entities.Entity building, Unity.Entities.Entity zone, System.Boolean omitBrand);
```

- `private GetStaticTransportStopName(Unity.Entities.Entity stop) : Game.UI.NameSystem+Name`  

```csharp
private Game.UI.NameSystem+Name GetStaticTransportStopName(Unity.Entities.Entity stop);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetCustomName(Unity.Entities.Entity entity, System.String name) : System.Void`  

```csharp
public System.Void SetCustomName(Unity.Entities.Entity entity, System.String name);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public TryGetCustomName(Unity.Entities.Entity entity, System.String& customName) : System.Boolean`  

```csharp
public System.Boolean TryGetCustomName(Unity.Entities.Entity entity, System.String& customName);
```


## Nested types

- `Game.UI.NameSystem+NameType`  
- `Game.UI.NameSystem+Name`  

