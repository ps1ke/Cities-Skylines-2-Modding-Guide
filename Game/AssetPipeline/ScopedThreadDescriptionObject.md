# Game.AssetPipeline.AssetImportPipeline+Progress+ScopedThreadDescriptionObject

**Assembly:** `Game`  
**Namespace:** `Game.AssetPipeline`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class ScopedThreadDescriptionObject : System.IDisposable
{
    private Game.AssetPipeline.AssetImportPipeline+Progress owner;

    public ScopedThreadDescriptionObject(Game.AssetPipeline.AssetImportPipeline+Progress owner, System.String description);

    public System.Void Dispose();
}
```


## Fields

- `private Game.AssetPipeline.AssetImportPipeline+Progress owner`  

```csharp
private Game.AssetPipeline.AssetImportPipeline+Progress owner;
```


## Constructors

- `public ScopedThreadDescriptionObject(Game.AssetPipeline.AssetImportPipeline+Progress owner, System.String description)`  

```csharp
public ScopedThreadDescriptionObject(Game.AssetPipeline.AssetImportPipeline+Progress owner, System.String description);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


