# Game.Modding.IMod

**Assembly:** `Game`  
**Namespace:** `Game.Modding`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IMod
{
    public abstract System.Void OnDispose();
    public abstract System.Void OnLoad(Game.UpdateSystem updateSystem);
}
```


## Methods

- `public abstract OnDispose() : System.Void`  

```csharp
public abstract System.Void OnDispose();
```

- `public abstract OnLoad(Game.UpdateSystem updateSystem) : System.Void`  

```csharp
public abstract System.Void OnLoad(Game.UpdateSystem updateSystem);
```


