# Game.Reflection.PrefabEntityListWrapper`1+PrefabEntityListWrapperEnumerator

**Assembly:** `Game`  
**Namespace:** `Game.Reflection`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.Collections.Generic.IEnumerator<T>`, `System.IDisposable`, `System.Collections.IEnumerator`  

## Code

```csharp
public class PrefabEntityListWrapperEnumerator<T> : System.Collections.Generic.IEnumerator<T>, System.IDisposable, System.Collections.IEnumerator
{
    private System.Int32 m_Index;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_Entities;

    public T Current { get; }
    private System.Object System.Collections.IEnumerator.Current { private get; }

    public PrefabEntityListWrapperEnumerator(Unity.Collections.NativeList<Unity.Entities.Entity> entities, Game.Prefabs.PrefabSystem prefabSystem);

    public System.Void Dispose();
    public System.Boolean MoveNext();
    public System.Void Reset();
}
```


## Fields

- `private System.Int32 m_Index`  

```csharp
private System.Int32 m_Index;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_Entities`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_Entities;
```


## Properties

- `public T Current { get }`  

```csharp
public T Current { get; }
```

- `private System.Object System.Collections.IEnumerator.Current { private get }`  

```csharp
private System.Object System.Collections.IEnumerator.Current { private get; }
```


## Constructors

- `public PrefabEntityListWrapperEnumerator(Unity.Collections.NativeList<Unity.Entities.Entity> entities, Game.Prefabs.PrefabSystem prefabSystem)`  

```csharp
public PrefabEntityListWrapperEnumerator(Unity.Collections.NativeList<Unity.Entities.Entity> entities, Game.Prefabs.PrefabSystem prefabSystem);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public MoveNext() : System.Boolean`  

```csharp
public System.Boolean MoveNext();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```


