# Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.InteriorMapping`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Room
{
    public System.Int32 Floor;
    public System.Int32 RoomID;
    public System.Int32 Facing;
    public System.Int32 RoomIndex;
    public UnityEngine.Bounds Bounds;
    public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window>> WindowMap;

    public Room();
    public Room(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);

    public System.Void AddWindow(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
    private System.Void AddWindow(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 key, Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor floor);
    public System.Boolean Merge(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room room, System.Single distance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
}
```


## Fields

- `public System.Int32 Floor`  

```csharp
public System.Int32 Floor;
```

- `public System.Int32 RoomID`  

```csharp
public System.Int32 RoomID;
```

- `public System.Int32 Facing`  

```csharp
public System.Int32 Facing;
```

- `public System.Int32 RoomIndex`  

```csharp
public System.Int32 RoomIndex;
```

- `public UnityEngine.Bounds Bounds`  

```csharp
public UnityEngine.Bounds Bounds;
```

- `public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window>> WindowMap`  

```csharp
public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window>> WindowMap;
```


## Constructors

- `public Room()`  

```csharp
public Room();
```

- `public Room(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors)`  

```csharp
public Room(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
```


## Methods

- `public AddWindow(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors) : System.Void`  

```csharp
public System.Void AddWindow(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
```

- `private AddWindow(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 key, Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor floor) : System.Void`  

```csharp
private System.Void AddWindow(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Window window, System.Int32 key, Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor floor);
```

- `public Merge(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room room, System.Single distance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors) : System.Boolean`  

```csharp
public System.Boolean Merge(Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room room, System.Single distance, System.Collections.Generic.List<Colossal.AssetPipeline.PostProcessors.InteriorMapping.Floor> floors);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.InteriorMapping.Room+RoomFacing`  

