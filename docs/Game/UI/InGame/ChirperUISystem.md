# Game.UI.InGame.ChirperUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ChirperUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.UI.InGame.InfoviewsUISystem m_InfoviewsUISystem;
    private Game.UI.InGame.ChirpLinkSystem m_ChirpLinkSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Unity.Entities.EntityQuery m_ModifiedChirpQuery;
    private Unity.Entities.EntityQuery m_CreatedChirpQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Colossal.UI.Binding.RawValueBinding m_ChirpsBinding;
    private Colossal.UI.Binding.RawEventBinding m_ChirpAddedBinding;
    private static const System.String kGroup;
    private static const System.Int32 kBrandIconSize;

    public ChirperUISystem();

    private System.Void AddLike(Unity.Entities.Entity entity);
    public System.Void BindChirp(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity chirpEntity, System.Boolean newChirp);
    private System.Void BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, System.Int32 linkIndex);
    public System.Void BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.UI.NameSystem+Name name);
    private System.Void BindChirpSender(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.String GetAvatar(Unity.Entities.Entity chirpEntity);
    public System.String GetMessageID(Unity.Entities.Entity chirp);
    private System.Int32 GetRandomIndex(Unity.Entities.Entity chirpEntity);
    private Unity.Collections.NativeArray<Unity.Entities.Entity> GetSortedChirps(Unity.Entities.EntityQuery chirpQuery);
    private System.UInt32 GetTicks(System.UInt32 frameIndex);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void PublishAddedChirps();
    private System.Void RemoveLike(Unity.Entities.Entity entity);
    private System.Void SelectLink(System.String target);
    private System.Void UpdateChirps(Colossal.UI.Binding.IJsonWriter binder);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.UI.InGame.InfoviewsUISystem m_InfoviewsUISystem`  

```csharp
private Game.UI.InGame.InfoviewsUISystem m_InfoviewsUISystem;
```

- `private Game.UI.InGame.ChirpLinkSystem m_ChirpLinkSystem`  

```csharp
private Game.UI.InGame.ChirpLinkSystem m_ChirpLinkSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedChirpQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Colossal.UI.Binding.RawValueBinding m_ChirpsBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ChirpsBinding;
```

- `private Colossal.UI.Binding.RawEventBinding m_ChirpAddedBinding`  

```csharp
private Colossal.UI.Binding.RawEventBinding m_ChirpAddedBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```

- `private static const System.Int32 kBrandIconSize`  

```csharp
private static const System.Int32 kBrandIconSize;
```


## Constructors

- `public ChirperUISystem()`  

```csharp
public ChirperUISystem();
```


## Methods

- `private AddLike(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void AddLike(Unity.Entities.Entity entity);
```

- `public BindChirp(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity chirpEntity, System.Boolean newChirp = False) : System.Void`  

```csharp
public System.Void BindChirp(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity chirpEntity, System.Boolean newChirp);
```

- `private BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, System.Int32 linkIndex) : System.Void`  

```csharp
private System.Void BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, System.Int32 linkIndex);
```

- `public BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.UI.NameSystem+Name name) : System.Void`  

```csharp
public System.Void BindChirpLink(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity, Game.UI.NameSystem+Name name);
```

- `private BindChirpSender(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindChirpSender(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `private GetAvatar(Unity.Entities.Entity chirpEntity) : System.String`  

```csharp
private System.String GetAvatar(Unity.Entities.Entity chirpEntity);
```

- `public GetMessageID(Unity.Entities.Entity chirp) : System.String`  

```csharp
public System.String GetMessageID(Unity.Entities.Entity chirp);
```

- `private GetRandomIndex(Unity.Entities.Entity chirpEntity) : System.Int32`  

```csharp
private System.Int32 GetRandomIndex(Unity.Entities.Entity chirpEntity);
```

- `private GetSortedChirps(Unity.Entities.EntityQuery chirpQuery) : Unity.Collections.NativeArray<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> GetSortedChirps(Unity.Entities.EntityQuery chirpQuery);
```

- `private GetTicks(System.UInt32 frameIndex) : System.UInt32`  

```csharp
private System.UInt32 GetTicks(System.UInt32 frameIndex);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PublishAddedChirps() : System.Void`  

```csharp
private System.Void PublishAddedChirps();
```

- `private RemoveLike(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void RemoveLike(Unity.Entities.Entity entity);
```

- `private SelectLink(System.String target) : System.Void`  

```csharp
private System.Void SelectLink(System.String target);
```

- `private UpdateChirps(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void UpdateChirps(Colossal.UI.Binding.IJsonWriter binder);
```


## Nested types

- `Game.UI.InGame.ChirperUISystem+ChirpComparer`  

