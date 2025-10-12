# Game.ArtPipeline.InteriorMappingProcessor+Room

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public System.Int32 Floor`  
- `public System.Int32 RoomID`  
- `public System.Int32 Facing`  
- `public System.Int32 RoomIndex`  
- `public UnityEngine.Bounds Bounds`  
- `public System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Window>> WindowMap`  

## Constructors

- `public Room()`  
- `public Room(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors)`  

## Methods

- `public AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors) : System.Void`  
- `private AddWindow(Game.ArtPipeline.InteriorMappingProcessor+Window window, System.Int32 key, Game.ArtPipeline.InteriorMappingProcessor+Floor floor) : System.Void`  
- `public Merge(Game.ArtPipeline.InteriorMappingProcessor+Room room, System.Single distance, System.Collections.Generic.List<Game.ArtPipeline.InteriorMappingProcessor+Floor> floors) : System.Boolean`  

