# Game.Tools.DefaultToolSystem+SelectEntityJob

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

## Code

```csharp
public sealed struct SelectEntityJob : Unity.Jobs.IJob
{
    public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_Chunks;
    public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
    public Unity.Entities.ComponentTypeHandle<Game.Objects.Attachment> m_AttachmentType;
    public Unity.Entities.ComponentTypeHandle<Game.Vehicles.Controller> m_ControllerType;
    public Unity.Entities.EntityStorageInfoLookup m_EntityLookup;
    public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
    public Unity.Entities.ComponentLookup<Game.Common.Target> m_TargetData;
    public Unity.Entities.ComponentLookup<Game.Tools.Debug> m_DebugData;
    public Unity.Entities.ComponentLookup<Game.Notifications.Icon> m_IconData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
    public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData;
    public System.Boolean m_DebugSelect;
    public Unity.Collections.NativeReference<Unity.Entities.Entity> m_Selected;
    public Unity.Entities.EntityCommandBuffer m_CommandBuffer;

    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_Chunks`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.ArchetypeChunk> m_Chunks;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Tools.Temp> m_TempType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Objects.Attachment> m_AttachmentType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Objects.Attachment> m_AttachmentType;
```

- `public Unity.Entities.ComponentTypeHandle<Game.Vehicles.Controller> m_ControllerType`  

```csharp
public Unity.Entities.ComponentTypeHandle<Game.Vehicles.Controller> m_ControllerType;
```

- `public Unity.Entities.EntityStorageInfoLookup m_EntityLookup`  

```csharp
public Unity.Entities.EntityStorageInfoLookup m_EntityLookup;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Target> m_TargetData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Target> m_TargetData;
```

- `public Unity.Entities.ComponentLookup<Game.Tools.Debug> m_DebugData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Tools.Debug> m_DebugData;
```

- `public Unity.Entities.ComponentLookup<Game.Notifications.Icon> m_IconData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Notifications.Icon> m_IconData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData;
```

- `public System.Boolean m_DebugSelect`  

```csharp
public System.Boolean m_DebugSelect;
```

- `public Unity.Collections.NativeReference<Unity.Entities.Entity> m_Selected`  

```csharp
public Unity.Collections.NativeReference<Unity.Entities.Entity> m_Selected;
```

- `public Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

```csharp
public Unity.Entities.EntityCommandBuffer m_CommandBuffer;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


