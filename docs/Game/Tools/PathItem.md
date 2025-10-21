# Game.Tools.NetToolSystem+PathItem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.ILessThan<Game.Tools.NetToolSystem+PathItem>`  

## Code

```csharp
public sealed struct PathItem : Colossal.Collections.ILessThan<Game.Tools.NetToolSystem+PathItem>
{
    public Unity.Entities.Entity m_Node;
    public Unity.Entities.Entity m_Edge;
    public System.Single m_Cost;

    public System.Boolean LessThan(Game.Tools.NetToolSystem+PathItem other);
}
```


## Fields

- `public Unity.Entities.Entity m_Node`  

```csharp
public Unity.Entities.Entity m_Node;
```

- `public Unity.Entities.Entity m_Edge`  

```csharp
public Unity.Entities.Entity m_Edge;
```

- `public System.Single m_Cost`  

```csharp
public System.Single m_Cost;
```


## Methods

- `public LessThan(Game.Tools.NetToolSystem+PathItem other) : System.Boolean`  

```csharp
public System.Boolean LessThan(Game.Tools.NetToolSystem+PathItem other);
```


