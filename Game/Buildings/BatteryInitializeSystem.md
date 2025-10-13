# Game.Buildings.BatteryInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatteryInitializeSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_Additions;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Buildings.BatteryInitializeSystem+TypeHandle __TypeHandle;

    public BatteryInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_Additions`  

```csharp
private Unity.Entities.EntityQuery m_Additions;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Buildings.BatteryInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.BatteryInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BatteryInitializeSystem()`  

```csharp
public BatteryInitializeSystem();
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Buildings.BatteryInitializeSystem+InitializeBatteryJob`  
- `Game.Buildings.BatteryInitializeSystem+TypeHandle`  

