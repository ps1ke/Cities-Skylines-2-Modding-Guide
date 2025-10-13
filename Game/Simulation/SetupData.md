# Game.Simulation.PathfindSetupSystem+SetupData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SetupData
{
    private System.Int32 m_StartIndex;
    private System.Int32 m_Length;
    private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupItems;
    private Game.Pathfind.PathfindTargetSeekerData m_SeekerData;
    private Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> m_TargetQueue;

    public System.Int32 Length { get; }

    public SetupData(System.Int32 startIndex, System.Int32 endIndex, Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> setupItems, Game.Pathfind.PathfindTargetSeekerData seekerData, Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> targetQueue);

    public System.Void GetItem(System.Int32 index, Unity.Entities.Entity& entity, Game.Pathfind.PathfindTargetSeeker`1[[Game.Simulation.PathfindSetupBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker);
    public System.Void GetItem(System.Int32 index, Unity.Entities.Entity& entity, Unity.Entities.Entity& owner, Game.Pathfind.PathfindTargetSeeker`1[[Game.Simulation.PathfindSetupBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker);
}
```


## Fields

- `private System.Int32 m_StartIndex`  

```csharp
private System.Int32 m_StartIndex;
```

- `private System.Int32 m_Length`  

```csharp
private System.Int32 m_Length;
```

- `private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupItems`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> m_SetupItems;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_SeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_SeekerData;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> m_TargetQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> m_TargetQueue;
```


## Properties

- `public System.Int32 Length { get }`  

```csharp
public System.Int32 Length { get; }
```


## Constructors

- `public SetupData(System.Int32 startIndex, System.Int32 endIndex, Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> setupItems, Game.Pathfind.PathfindTargetSeekerData seekerData, Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> targetQueue)`  

```csharp
public SetupData(System.Int32 startIndex, System.Int32 endIndex, Unity.Collections.NativeList<Game.Simulation.PathfindSetupSystem+SetupListItem> setupItems, Game.Pathfind.PathfindTargetSeekerData seekerData, Unity.Collections.NativeQueue<Game.Simulation.PathfindSetupTarget> targetQueue);
```


## Methods

- `public GetItem(System.Int32 index, Unity.Entities.Entity& entity, Game.Pathfind.PathfindTargetSeeker`1[[Game.Simulation.PathfindSetupBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker) : System.Void`  

```csharp
public System.Void GetItem(System.Int32 index, Unity.Entities.Entity& entity, Game.Pathfind.PathfindTargetSeeker`1[[Game.Simulation.PathfindSetupBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker);
```

- `public GetItem(System.Int32 index, Unity.Entities.Entity& entity, Unity.Entities.Entity& owner, Game.Pathfind.PathfindTargetSeeker`1[[Game.Simulation.PathfindSetupBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker) : System.Void`  

```csharp
public System.Void GetItem(System.Int32 index, Unity.Entities.Entity& entity, Unity.Entities.Entity& owner, Game.Pathfind.PathfindTargetSeeker`1[[Game.Simulation.PathfindSetupBuffer, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& targetSeeker);
```


