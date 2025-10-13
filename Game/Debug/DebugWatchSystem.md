# Game.Debug.DebugWatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class DebugWatchSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+ManagedSystemState> m_ManagedSystemStates;
    private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> m_Watches;
    private System.UInt32 m_LastFrameIndex;
    private System.Boolean m_WatchesChanged;
    private static readonly System.String[] colors;

    public System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> watches { get; }
    public System.Boolean watchesChanged { get; }

    public DebugWatchSystem();

    internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__Value|15_3(System.String name, Game.Reflection.IValueAccessor accessor);
    internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__ValueContainer|15_2(System.String name, Game.Reflection.IValueAccessor accessor);
    public System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSystemFoldouts();
    public System.Void ClearWatches();
    public System.Void ClearWatchesChanged();
    public static Game.Reflection.IValueAccessor CreateTypedAccessor(Game.Reflection.IValueAccessor accessor);
    private static System.String GetArrayItemName(System.Reflection.MemberInfo member, System.Int32 index);
    private static System.Reflection.FieldInfo[] GetWatchDepsFields(System.Type systemType);
    private static System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo> GetWatchValueMembers(System.Type systemType);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+ManagedSystemState> m_ManagedSystemStates`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+ManagedSystemState> m_ManagedSystemStates;
```

- `private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> m_Watches`  

```csharp
private System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> m_Watches;
```

- `private System.UInt32 m_LastFrameIndex`  

```csharp
private System.UInt32 m_LastFrameIndex;
```

- `private System.Boolean m_WatchesChanged`  

```csharp
private System.Boolean m_WatchesChanged;
```

- `private static readonly System.String[] colors`  

```csharp
private static readonly System.String[] colors;
```


## Properties

- `public System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> watches { get }`  

```csharp
public System.Collections.Generic.List<Game.Debug.DebugWatchSystem+Watch> watches { get; }
```

- `public System.Boolean watchesChanged { get }`  

```csharp
public System.Boolean watchesChanged { get; }
```


## Constructors

- `public DebugWatchSystem()`  

```csharp
public DebugWatchSystem();
```


## Methods

- `internal static <BuildSystemFoldouts>g__Value|15_3(System.String name, Game.Reflection.IValueAccessor accessor) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__Value|15_3(System.String name, Game.Reflection.IValueAccessor accessor);
```

- `internal static <BuildSystemFoldouts>g__ValueContainer|15_2(System.String name, Game.Reflection.IValueAccessor accessor) : UnityEngine.Rendering.DebugUI+Widget`  

```csharp
internal static UnityEngine.Rendering.DebugUI+Widget <BuildSystemFoldouts>g__ValueContainer|15_2(System.String name, Game.Reflection.IValueAccessor accessor);
```

- `public BuildSystemFoldouts() : System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget>`  

```csharp
public System.Collections.Generic.List<UnityEngine.Rendering.DebugUI+Widget> BuildSystemFoldouts();
```

- `public ClearWatches() : System.Void`  

```csharp
public System.Void ClearWatches();
```

- `public ClearWatchesChanged() : System.Void`  

```csharp
public System.Void ClearWatchesChanged();
```

- `public static CreateTypedAccessor(Game.Reflection.IValueAccessor accessor) : Game.Reflection.IValueAccessor`  

```csharp
public static Game.Reflection.IValueAccessor CreateTypedAccessor(Game.Reflection.IValueAccessor accessor);
```

- `private static GetArrayItemName(System.Reflection.MemberInfo member, System.Int32 index) : System.String`  

```csharp
private static System.String GetArrayItemName(System.Reflection.MemberInfo member, System.Int32 index);
```

- `private static GetWatchDepsFields(System.Type systemType) : System.Reflection.FieldInfo[]`  

```csharp
private static System.Reflection.FieldInfo[] GetWatchDepsFields(System.Type systemType);
```

- `private static GetWatchValueMembers(System.Type systemType) : System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo>`  

```csharp
private static System.Collections.Generic.IEnumerable<System.Reflection.MemberInfo> GetWatchValueMembers(System.Type systemType);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Debug.DebugWatchSystem+ManagedSystemState`  
- `Game.Debug.DebugWatchSystem+Watch`  
- `Game.Debug.DebugWatchSystem+HistoryWatch<T>`  
- `Game.Debug.DebugWatchSystem+DistributionWatch`  
- `Game.Debug.DebugWatchSystem+<>c`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass11_0`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_0`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_1`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_2`  
- `Game.Debug.DebugWatchSystem+<>c__DisplayClass15_3`  

