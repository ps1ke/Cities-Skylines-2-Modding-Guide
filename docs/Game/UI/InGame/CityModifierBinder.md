# Game.UI.InGame.PrefabUISystem+CityModifierBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder`  

## Code

```csharp
public class CityModifierBinder : Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder
{
    public CityModifierBinder();

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static System.Void Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T cityModifiers);
    public static System.String GetModifierUnit(Game.Prefabs.CityModifierData data);
    private static System.Boolean IsValidModifierType(Game.City.CityModifierType type);
    public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public CityModifierBinder()`  

```csharp
public CityModifierBinder();
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T cityModifiers) : System.Void`  

```csharp
public static System.Void Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T cityModifiers);
```

- `public static GetModifierUnit(Game.Prefabs.CityModifierData data) : System.String`  

```csharp
public static System.String GetModifierUnit(Game.Prefabs.CityModifierData data);
```

- `private static IsValidModifierType(Game.City.CityModifierType type) : System.Boolean`  

```csharp
private static System.Boolean IsValidModifierType(Game.City.CityModifierType type);
```

- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


