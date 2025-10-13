# Game.Simulation.PathfindSetupSystem+SetupListItem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Simulation.PathfindSetupSystem+SetupListItem>`  

## Code

```csharp
public sealed struct SetupListItem : System.IComparable<Game.Simulation.PathfindSetupSystem+SetupListItem>
{
    public Game.Pathfind.SetupQueueTarget m_Target;
    public Game.Pathfind.PathfindParameters m_Parameters;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_Buffer;
    public Unity.Entities.Entity m_Owner;
    public Game.Common.RandomSeed m_RandomSeed;
    public System.Int32 m_ActionIndex;
    public System.Boolean m_ActionStart;

    public SetupListItem(Game.Pathfind.SetupQueueTarget target, Game.Pathfind.PathfindParameters parameters, Unity.Entities.Entity owner, Game.Common.RandomSeed randomSeed, System.Int32 actionIndex, System.Boolean actionStart);

    public System.Int32 CompareTo(Game.Simulation.PathfindSetupSystem+SetupListItem other);
}
```


## Fields

- `public Game.Pathfind.SetupQueueTarget m_Target`  

```csharp
public Game.Pathfind.SetupQueueTarget m_Target;
```

- `public Game.Pathfind.PathfindParameters m_Parameters`  

```csharp
public Game.Pathfind.PathfindParameters m_Parameters;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_Buffer`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.PathTarget> m_Buffer;
```

- `public Unity.Entities.Entity m_Owner`  

```csharp
public Unity.Entities.Entity m_Owner;
```

- `public Game.Common.RandomSeed m_RandomSeed`  

```csharp
public Game.Common.RandomSeed m_RandomSeed;
```

- `public System.Int32 m_ActionIndex`  

```csharp
public System.Int32 m_ActionIndex;
```

- `public System.Boolean m_ActionStart`  

```csharp
public System.Boolean m_ActionStart;
```


## Constructors

- `public SetupListItem(Game.Pathfind.SetupQueueTarget target, Game.Pathfind.PathfindParameters parameters, Unity.Entities.Entity owner, Game.Common.RandomSeed randomSeed, System.Int32 actionIndex, System.Boolean actionStart)`  

```csharp
public SetupListItem(Game.Pathfind.SetupQueueTarget target, Game.Pathfind.PathfindParameters parameters, Unity.Entities.Entity owner, Game.Common.RandomSeed randomSeed, System.Int32 actionIndex, System.Boolean actionStart);
```


## Methods

- `public CompareTo(Game.Simulation.PathfindSetupSystem+SetupListItem other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.Simulation.PathfindSetupSystem+SetupListItem other);
```


