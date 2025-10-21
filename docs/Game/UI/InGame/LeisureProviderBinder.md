# Game.UI.InGame.PrefabUISystem+LeisureProviderBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder`  

## Code

```csharp
public class LeisureProviderBinder : Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder
{
    public LeisureProviderBinder();

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static System.Void Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T providers);
    public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public LeisureProviderBinder()`  

```csharp
public LeisureProviderBinder();
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T providers) : System.Void`  

```csharp
public static System.Void Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T providers);
```

- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


