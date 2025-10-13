# Game.Debug.TradeCostDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TradeCostDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_StorageGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Economy.Resource m_SelectedResource;
    private Game.Debug.BaseDebugSystem+Option m_StorageOption;
    private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
    private Game.Debug.TradeCostDebugSystem+TypeHandle __TypeHandle;

    public TradeCostDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 <OnEnabled>b__6_0();
    private System.Void <OnEnabled>b__6_1(System.Int32 value);
    private System.Int32 <OnEnabled>b__6_2();
    private System.Void <OnEnabled>b__6_3(System.Int32 value);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_StorageGroup`  

```csharp
private Unity.Entities.EntityQuery m_StorageGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Economy.Resource m_SelectedResource`  

```csharp
private Game.Economy.Resource m_SelectedResource;
```

- `private Game.Debug.BaseDebugSystem+Option m_StorageOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StorageOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CompanyOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
```

- `private Game.Debug.TradeCostDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.TradeCostDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TradeCostDebugSystem()`  

```csharp
public TradeCostDebugSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private <OnEnabled>b__6_0() : System.Int32`  

```csharp
private System.Int32 <OnEnabled>b__6_0();
```

- `private <OnEnabled>b__6_1(System.Int32 value) : System.Void`  

```csharp
private System.Void <OnEnabled>b__6_1(System.Int32 value);
```

- `private <OnEnabled>b__6_2() : System.Int32`  

```csharp
private System.Int32 <OnEnabled>b__6_2();
```

- `private <OnEnabled>b__6_3(System.Int32 value) : System.Void`  

```csharp
private System.Void <OnEnabled>b__6_3(System.Int32 value);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Debug.TradeCostDebugSystem+TradeCostGizmoJob`  
- `Game.Debug.TradeCostDebugSystem+TypeHandle`  

