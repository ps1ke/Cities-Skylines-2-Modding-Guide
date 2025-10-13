# Game.AssetPipeline.IPrefabFactory

**Assembly:** `Game`  
**Namespace:** `Game.AssetPipeline`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IPrefabFactory
{
    public abstract T CreatePrefab<T>(System.String sourcePath, System.String name, System.Int32 lodLevel);
}
```


## Methods

- `public abstract CreatePrefab<T>(System.String sourcePath, System.String name, System.Int32 lodLevel) : T`  

```csharp
public abstract T CreatePrefab<T>(System.String sourcePath, System.String name, System.Int32 lodLevel);
```


