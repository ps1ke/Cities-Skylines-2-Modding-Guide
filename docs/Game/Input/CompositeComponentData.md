# Game.Input.InputManager+CompositeComponentData

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct CompositeComponentData
{
    public readonly Game.Input.ActionComponent m_Component;
    public readonly System.String m_BindingName;
    public readonly System.String m_ModifierName;
    public static Game.Input.InputManager+CompositeComponentData defaultData;

    public CompositeComponentData(Game.Input.ActionComponent component, System.String bindingName, System.String modifierName);

}
```


## Fields

- `public readonly Game.Input.ActionComponent m_Component`  

```csharp
public readonly Game.Input.ActionComponent m_Component;
```

- `public readonly System.String m_BindingName`  

```csharp
public readonly System.String m_BindingName;
```

- `public readonly System.String m_ModifierName`  

```csharp
public readonly System.String m_ModifierName;
```

- `public static Game.Input.InputManager+CompositeComponentData defaultData`  

```csharp
public static Game.Input.InputManager+CompositeComponentData defaultData;
```


## Constructors

- `public CompositeComponentData(Game.Input.ActionComponent component, System.String bindingName, System.String modifierName)`  

```csharp
public CompositeComponentData(Game.Input.ActionComponent component, System.String bindingName, System.String modifierName);
```


