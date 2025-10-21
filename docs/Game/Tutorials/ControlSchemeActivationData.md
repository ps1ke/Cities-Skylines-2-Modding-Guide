# Game.Tutorials.ControlSchemeActivationData

**Assembly:** `Game`  
**Namespace:** `Game.Tutorials`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ControlSchemeActivationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Input.InputManager+ControlScheme m_ControlScheme;

    public ControlSchemeActivationData(Game.Input.InputManager+ControlScheme controlScheme);

}
```


## Fields

- `public Game.Input.InputManager+ControlScheme m_ControlScheme`  

```csharp
public Game.Input.InputManager+ControlScheme m_ControlScheme;
```


## Constructors

- `public ControlSchemeActivationData(Game.Input.InputManager+ControlScheme controlScheme)`  

```csharp
public ControlSchemeActivationData(Game.Input.InputManager+ControlScheme controlScheme);
```


