# Game.UI.InGame.LandValueInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageLandValue;
    private Unity.Entities.EntityQuery m_LandValueQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }

    public LandValueInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void UpdateLandValue();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageLandValue`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageLandValue;
```

- `private Unity.Entities.EntityQuery m_LandValueQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public LandValueInfoviewUISystem()`  

```csharp
public LandValueInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected virtual System.Void PerformUpdate();
```

- `private UpdateLandValue() : System.Void`  

```csharp
private System.Void UpdateLandValue();
```


## Nested types

- `Game.UI.InGame.LandValueInfoviewUISystem+CalculateAverageLandValueJob`  
- `Game.UI.InGame.LandValueInfoviewUISystem+TypeHandle`  

