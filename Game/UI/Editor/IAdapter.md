# Game.UI.Editor.SeasonWheel+IAdapter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IAdapter
{
    public Unity.Entities.Entity selectedSeason { get; set; }
    public System.Collections.Generic.IEnumerable<Game.UI.Editor.SeasonWheel+Season> seasons { get; }

    public abstract System.Void SetStartTimeOfYear(Unity.Entities.Entity season, Colossal.Mathematics.Bounds1 startTimeOfYear);
}
```


## Properties

- `public Unity.Entities.Entity selectedSeason { get; set }`  

```csharp
public Unity.Entities.Entity selectedSeason { get; set; }
```

- `public System.Collections.Generic.IEnumerable<Game.UI.Editor.SeasonWheel+Season> seasons { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Game.UI.Editor.SeasonWheel+Season> seasons { get; }
```


## Methods

- `public abstract SetStartTimeOfYear(Unity.Entities.Entity season, Colossal.Mathematics.Bounds1 startTimeOfYear) : System.Void`  

```csharp
public abstract System.Void SetStartTimeOfYear(Unity.Entities.Entity season, Colossal.Mathematics.Bounds1 startTimeOfYear);
```


