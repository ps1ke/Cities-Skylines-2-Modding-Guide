# Game.ArtPipeline.InteriorMappingProcessor+Room

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

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
    public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window>> WindowMap;

    public Room();
    public Room(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors);

    public System.Void AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors);
    private System.Void AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Int32 key, Game.ArtPipeline.InteriorMappingProcessor+Floor floor);
    public System.Boolean Merge(Game.ArtPipeline.InteriorMappingProcessor+Room room, System.Single distance, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors);
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

- `public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window>> WindowMap`  

```csharp
public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window>> WindowMap;
```


## Constructors

- `public Room()`  

```csharp
public Room();
```

- `public Room(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors)`  

```csharp
public Room(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors);
```


## Methods

- `public AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors) : System.Void`  

```csharp
public System.Void AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors);
```

- `private AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Int32 key, Game.ArtPipeline.InteriorMappingProcessor+Floor floor) : System.Void`  

```csharp
private System.Void AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Int32 key, Game.ArtPipeline.InteriorMappingProcessor+Floor floor);
```

- `public Merge(Game.ArtPipeline.InteriorMappingProcessor+Room room, System.Single distance, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors) : System.Boolean`  

```csharp
public System.Boolean Merge(Game.ArtPipeline.InteriorMappingProcessor+Room room, System.Single distance, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors);
```


