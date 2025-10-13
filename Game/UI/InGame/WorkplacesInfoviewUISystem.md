# Game.UI.InGame.WorkplacesInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkplacesInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_WorkplaceQuery;
    private Unity.Entities.EntityQuery m_WorkplaceModifiedQuery;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_EmployeesData;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_WorkplacesData;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workplaces;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workers;
    private Unity.Collections.NativeArray<System.Int32> m_IntResults;
    private Unity.Collections.NativeArray<Game.UI.InGame.EmploymentData> m_EmploymentDataResults;
    private Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public WorkplacesInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.UI.InGame.EmploymentData GetEmployeesData();
    private System.Int32 GetWorkers();
    private System.Int32 GetWorkplaces();
    private Game.UI.InGame.EmploymentData GetWorkplacesData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_WorkplaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceQuery;
```

- `private Unity.Entities.EntityQuery m_WorkplaceModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceModifiedQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_EmployeesData`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_EmployeesData;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_WorkplacesData`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.EmploymentData> m_WorkplacesData;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workplaces`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workplaces;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workers`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Workers;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IntResults`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IntResults;
```

- `private Unity.Collections.NativeArray<Game.UI.InGame.EmploymentData> m_EmploymentDataResults`  

```csharp
private Unity.Collections.NativeArray<Game.UI.InGame.EmploymentData> m_EmploymentDataResults;
```

- `private Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle __TypeHandle;
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

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public WorkplacesInfoviewUISystem()`  

```csharp
public WorkplacesInfoviewUISystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetEmployeesData() : Game.UI.InGame.EmploymentData`  

```csharp
private Game.UI.InGame.EmploymentData GetEmployeesData();
```

- `private GetWorkers() : System.Int32`  

```csharp
private System.Int32 GetWorkers();
```

- `private GetWorkplaces() : System.Int32`  

```csharp
private System.Int32 GetWorkplaces();
```

- `private GetWorkplacesData() : Game.UI.InGame.EmploymentData`  

```csharp
private Game.UI.InGame.EmploymentData GetWorkplacesData();
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

- `private ResetResults() : System.Void`  

```csharp
private System.Void ResetResults();
```


## Nested types

- `Game.UI.InGame.WorkplacesInfoviewUISystem+Result`  
- `Game.UI.InGame.WorkplacesInfoviewUISystem+CalculateWorkplaceDataJob`  
- `Game.UI.InGame.WorkplacesInfoviewUISystem+TypeHandle`  

