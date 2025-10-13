# Game.UI.InGame.VehicleUIUtils+EntityWrapper

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct EntityWrapper
{
    private readonly Unity.Entities.Entity <entity>k__BackingField;

    public Unity.Entities.Entity entity { get; }

    public EntityWrapper(Unity.Entities.Entity entity);

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer, Game.UI.NameSystem nameSystem);
}
```


## Fields

- `private readonly Unity.Entities.Entity <entity>k__BackingField`  

```csharp
private readonly Unity.Entities.Entity <entity>k__BackingField;
```


## Properties

- `public Unity.Entities.Entity entity { get }`  

```csharp
public Unity.Entities.Entity entity { get; }
```


## Constructors

- `public EntityWrapper(Unity.Entities.Entity entity)`  

```csharp
public EntityWrapper(Unity.Entities.Entity entity);
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer, Game.UI.NameSystem nameSystem) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer, Game.UI.NameSystem nameSystem);
```


