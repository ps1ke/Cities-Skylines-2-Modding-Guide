# Game.Prefabs.TutorialBalloonPrefab+BalloonUITarget

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `Serializable`  

## Code

```csharp
public class BalloonUITarget : Colossal.UI.Binding.IJsonWritable
{
    public Game.Prefabs.PrefabBase m_UITagProvider;
    public Game.Prefabs.TutorialBalloonPrefab+BalloonDirection m_BalloonDirection;
    public Game.Prefabs.TutorialBalloonPrefab+BalloonAlignment m_BalloonAlignment;

    public BalloonUITarget();

    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `public Game.Prefabs.PrefabBase m_UITagProvider`  

```csharp
public Game.Prefabs.PrefabBase m_UITagProvider;
```

- `public Game.Prefabs.TutorialBalloonPrefab+BalloonDirection m_BalloonDirection`  

```csharp
public Game.Prefabs.TutorialBalloonPrefab+BalloonDirection m_BalloonDirection;
```

- `public Game.Prefabs.TutorialBalloonPrefab+BalloonAlignment m_BalloonAlignment`  

```csharp
public Game.Prefabs.TutorialBalloonPrefab+BalloonAlignment m_BalloonAlignment;
```


## Constructors

- `public BalloonUITarget()`  

```csharp
public BalloonUITarget();
```


## Methods

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


