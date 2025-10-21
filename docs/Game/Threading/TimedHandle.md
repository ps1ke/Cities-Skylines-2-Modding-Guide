# Game.Threading.TimedScope+TimedHandle

**Assembly:** `Colossal.Core`  
**Namespace:** `Game.Threading`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct TimedHandle
{
    private readonly System.Diagnostics.Stopwatch m_StopWatch;
    private readonly System.TimeSpan m_Duration;

    public TimedHandle(System.TimeSpan duration);

    public System.Threading.Tasks.Task WaitRemainingTime();
}
```


## Fields

- `private readonly System.Diagnostics.Stopwatch m_StopWatch`  

```csharp
private readonly System.Diagnostics.Stopwatch m_StopWatch;
```

- `private readonly System.TimeSpan m_Duration`  

```csharp
private readonly System.TimeSpan m_Duration;
```


## Constructors

- `public TimedHandle(System.TimeSpan duration)`  

```csharp
public TimedHandle(System.TimeSpan duration);
```


## Methods

- `public WaitRemainingTime() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task WaitRemainingTime();
```


## Nested types

- `Game.Threading.TimedScope+TimedHandle+<WaitRemainingTime>d__3`  

