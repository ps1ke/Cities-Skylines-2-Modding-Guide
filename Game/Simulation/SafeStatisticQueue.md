# Game.Simulation.CityStatisticsSystem+SafeStatisticQueue

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SafeStatisticQueue
{
    private Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsEventQueue;
    public System.Boolean m_StatisticsEnabled;

    public SafeStatisticQueue(Unity.Collections.NativeQueue<Game.City.StatisticsEvent> queue, System.Boolean enabled);

    public System.Void Enqueue(Game.City.StatisticsEvent statisticsEvent);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsEventQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.City.StatisticsEvent> m_StatisticsEventQueue;
```

- `public System.Boolean m_StatisticsEnabled`  

```csharp
public System.Boolean m_StatisticsEnabled;
```


## Constructors

- `public SafeStatisticQueue(Unity.Collections.NativeQueue<Game.City.StatisticsEvent> queue, System.Boolean enabled)`  

```csharp
public SafeStatisticQueue(Unity.Collections.NativeQueue<Game.City.StatisticsEvent> queue, System.Boolean enabled);
```


## Methods

- `public Enqueue(Game.City.StatisticsEvent statisticsEvent) : System.Void`  

```csharp
public System.Void Enqueue(Game.City.StatisticsEvent statisticsEvent);
```


