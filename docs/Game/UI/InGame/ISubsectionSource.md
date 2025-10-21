# Game.UI.InGame.ISubsectionSource

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** interface abstract public  

**Implements:** `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract interface ISubsectionSource : Colossal.UI.Binding.IJsonWritable
{
    public abstract System.Boolean DisplayFor(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
    public abstract System.Void OnRequestUpdate(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
}
```


## Methods

- `public abstract DisplayFor(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Boolean`  

```csharp
public abstract System.Boolean DisplayFor(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```

- `public abstract OnRequestUpdate(Unity.Entities.Entity entity, Unity.Entities.Entity prefab) : System.Void`  

```csharp
public abstract System.Void OnRequestUpdate(Unity.Entities.Entity entity, Unity.Entities.Entity prefab);
```


