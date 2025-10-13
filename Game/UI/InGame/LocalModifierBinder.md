# Game.UI.InGame.PrefabUISystem+LocalModifierBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder`  

## Code

```csharp
public class LocalModifierBinder : Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder
{
    public LocalModifierBinder();

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static System.Void Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T localModifiers);
    public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public LocalModifierBinder()`  

```csharp
public LocalModifierBinder();
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T localModifiers) : System.Void`  

```csharp
public static System.Void Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T localModifiers);
```

- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


