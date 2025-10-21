# Game.UI.InGame.LifePathUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LifePathUISystem : Game.UI.UISystemBase
{
    private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.UI.InGame.ChirperUISystem m_ChirperUISystem;
    private Unity.Entities.EntityQuery m_FollowedQuery;
    private Unity.Entities.EntityQuery m_HappinessParameterQuery;
    private System.Int32 m_FollowedVersion;
    private System.Int32 m_LifePathEntryVersion;
    private System.Int32 m_ChirpVersion;
    private Colossal.UI.Binding.RawValueBinding m_FollowedCitizensBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathDetailsBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathItemsBinding;
    private static const System.String kGroup;

    public LifePathUISystem();

    private System.Void <OnCreate>b__13_0(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
    private System.Void <OnCreate>b__13_1(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
    private System.Void BindFollowedCitizens(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindLifePathDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindLifePathEvent(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
    private System.Void BindLifePathItems(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
    private System.Void FollowCitizen(Unity.Entities.Entity citizen);
    private System.Int32 GetRandomIndex(Unity.Entities.Entity entity);
    private Unity.Collections.NativeArray<Unity.Entities.Entity> GetSortedFollowedCitizens();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    private System.Void UnfollowCitizen(Unity.Entities.Entity citizen);
}
```


## Fields

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  

```csharp
private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.UI.InGame.ChirperUISystem m_ChirperUISystem`  

```csharp
private Game.UI.InGame.ChirperUISystem m_ChirperUISystem;
```

- `private Unity.Entities.EntityQuery m_FollowedQuery`  

```csharp
private Unity.Entities.EntityQuery m_FollowedQuery;
```

- `private Unity.Entities.EntityQuery m_HappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HappinessParameterQuery;
```

- `private System.Int32 m_FollowedVersion`  

```csharp
private System.Int32 m_FollowedVersion;
```

- `private System.Int32 m_LifePathEntryVersion`  

```csharp
private System.Int32 m_LifePathEntryVersion;
```

- `private System.Int32 m_ChirpVersion`  

```csharp
private System.Int32 m_ChirpVersion;
```

- `private Colossal.UI.Binding.RawValueBinding m_FollowedCitizensBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_FollowedCitizensBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathDetailsBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathItemsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_LifePathItemsBinding;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public LifePathUISystem()`  

```csharp
public LifePathUISystem();
```


## Methods

- `private <OnCreate>b__13_0(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  

```csharp
private System.Void <OnCreate>b__13_0(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
```

- `private <OnCreate>b__13_1(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  

```csharp
private System.Void <OnCreate>b__13_1(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
```

- `private BindFollowedCitizens(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindFollowedCitizens(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindLifePathDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindLifePathDetails(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `private BindLifePathEvent(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void BindLifePathEvent(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity entity);
```

- `private BindLifePathItems(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen) : System.Void`  

```csharp
private System.Void BindLifePathItems(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.Entity citizen);
```

- `private FollowCitizen(Unity.Entities.Entity citizen) : System.Void`  

```csharp
private System.Void FollowCitizen(Unity.Entities.Entity citizen);
```

- `private GetRandomIndex(Unity.Entities.Entity entity) : System.Int32`  

```csharp
private System.Int32 GetRandomIndex(Unity.Entities.Entity entity);
```

- `private GetSortedFollowedCitizens() : Unity.Collections.NativeArray<Unity.Entities.Entity>`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> GetSortedFollowedCitizens();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private UnfollowCitizen(Unity.Entities.Entity citizen) : System.Void`  

```csharp
private System.Void UnfollowCitizen(Unity.Entities.Entity citizen);
```


## Nested types

- `Game.UI.InGame.LifePathUISystem+FollowedCitizenComparer`  

