# Game.UI.InGame.PrefabUISystem+PollutionBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class PollutionBinder : Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    private Game.Prefabs.UIPollutionConfigurationPrefab m_ConfigData;

    public PollutionBinder(Game.Prefabs.UIPollutionConfigurationPrefab data);

    public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.Prefabs.UIPollutionConfigurationPrefab m_ConfigData`  

```csharp
private Game.Prefabs.UIPollutionConfigurationPrefab m_ConfigData;
```


## Constructors

- `public PollutionBinder(Game.Prefabs.UIPollutionConfigurationPrefab data)`  

```csharp
public PollutionBinder(Game.Prefabs.UIPollutionConfigurationPrefab data);
```


## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


