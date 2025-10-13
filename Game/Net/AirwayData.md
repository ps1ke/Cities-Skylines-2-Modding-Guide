# Game.Net.AirwayHelpers+AirwayData

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct AirwayData : System.IDisposable
{
    private Game.Net.AirwayHelpers+AirwayMap <helicopterMap>k__BackingField;
    private Game.Net.AirwayHelpers+AirwayMap <airplaneMap>k__BackingField;

    public Game.Net.AirwayHelpers+AirwayMap helicopterMap { get; private set; }
    public Game.Net.AirwayHelpers+AirwayMap airplaneMap { get; private set; }

    public AirwayData(Game.Net.AirwayHelpers+AirwayMap _helicopterMap, Game.Net.AirwayHelpers+AirwayMap _airplaneMap);

    public System.Void Dispose();
}
```


## Fields

- `private Game.Net.AirwayHelpers+AirwayMap <helicopterMap>k__BackingField`  

```csharp
private Game.Net.AirwayHelpers+AirwayMap <helicopterMap>k__BackingField;
```

- `private Game.Net.AirwayHelpers+AirwayMap <airplaneMap>k__BackingField`  

```csharp
private Game.Net.AirwayHelpers+AirwayMap <airplaneMap>k__BackingField;
```


## Properties

- `public Game.Net.AirwayHelpers+AirwayMap helicopterMap { get; private set }`  

```csharp
public Game.Net.AirwayHelpers+AirwayMap helicopterMap { get; private set; }
```

- `public Game.Net.AirwayHelpers+AirwayMap airplaneMap { get; private set }`  

```csharp
public Game.Net.AirwayHelpers+AirwayMap airplaneMap { get; private set; }
```


## Constructors

- `public AirwayData(Game.Net.AirwayHelpers+AirwayMap _helicopterMap, Game.Net.AirwayHelpers+AirwayMap _airplaneMap)`  

```csharp
public AirwayData(Game.Net.AirwayHelpers+AirwayMap _helicopterMap, Game.Net.AirwayHelpers+AirwayMap _airplaneMap);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```


