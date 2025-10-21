# Game.UI.InGame.SignatureBuildingUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SignatureBuildingUISystem : Game.UI.UISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_UnlockedSignatureBuildingQuery;
    private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_UnlockSignaturesBinding;
    private System.Boolean m_SkipUpdate;
    private System.Int32 m_LastListCount;
    private System.Boolean m_NeedTriggerUpdate;
    private static const System.String kGroup;

    public SignatureBuildingUISystem();

    public System.Void AddUnlockedSignature(Unity.Entities.Entity prefab);
    public System.Void ClearUnlockedSignature();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void RemoveUnlockedSignature();
    public System.Void SkipUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_UnlockedSignatureBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedSignatureBuildingQuery;
```

- `private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_UnlockSignaturesBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Collections.Generic.List<Unity.Entities.Entity>> m_UnlockSignaturesBinding;
```

- `private System.Boolean m_SkipUpdate`  

```csharp
private System.Boolean m_SkipUpdate;
```

- `private System.Int32 m_LastListCount`  

```csharp
private System.Int32 m_LastListCount;
```

- `private System.Boolean m_NeedTriggerUpdate`  

```csharp
private System.Boolean m_NeedTriggerUpdate;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public SignatureBuildingUISystem()`  

```csharp
public SignatureBuildingUISystem();
```


## Methods

- `public AddUnlockedSignature(Unity.Entities.Entity prefab) : System.Void`  

```csharp
public System.Void AddUnlockedSignature(Unity.Entities.Entity prefab);
```

- `public ClearUnlockedSignature() : System.Void`  

```csharp
public System.Void ClearUnlockedSignature();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private RemoveUnlockedSignature() : System.Void`  

```csharp
private System.Void RemoveUnlockedSignature();
```

- `public SkipUpdate() : System.Void`  

```csharp
public System.Void SkipUpdate();
```


