# Game.UI.InGame.PrefabUISystem+TransportStopBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class TransportStopBinder : Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public TransportStopBinder();

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    private static System.Boolean IsValidTransportType(Game.Prefabs.TransportType type);
    public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public TransportStopBinder()`  

```csharp
public TransportStopBinder();
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `private static IsValidTransportType(Game.Prefabs.TransportType type) : System.Boolean`  

```csharp
private static System.Boolean IsValidTransportType(Game.Prefabs.TransportType type);
```

- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


