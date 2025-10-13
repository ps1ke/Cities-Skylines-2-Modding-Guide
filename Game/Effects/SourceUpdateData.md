# Game.Effects.SourceUpdateData

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct SourceUpdateData
{
    private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue;

    public SourceUpdateData(Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> sourceUpdateQueue);

    public System.Void Add(Unity.Entities.Entity entity, Game.Objects.Transform transform);
    public System.Void Add(Game.Effects.SourceInfo sourceInfo);
    public System.Void AddSnap();
    public System.Void AddTemp(Unity.Entities.Entity prefab, Game.Objects.Transform transform);
    public System.Void Remove(Unity.Entities.Entity entity);
    public System.Void Remove(Game.Effects.SourceInfo sourceInfo);
    public System.Void WrongPrefab(Game.Effects.SourceInfo sourceInfo);
}
```


## Fields

- `private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue;
```


## Constructors

- `public SourceUpdateData(Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> sourceUpdateQueue)`  

```csharp
public SourceUpdateData(Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> sourceUpdateQueue);
```


## Methods

- `public Add(Unity.Entities.Entity entity, Game.Objects.Transform transform) : System.Void`  

```csharp
public System.Void Add(Unity.Entities.Entity entity, Game.Objects.Transform transform);
```

- `public Add(Game.Effects.SourceInfo sourceInfo) : System.Void`  

```csharp
public System.Void Add(Game.Effects.SourceInfo sourceInfo);
```

- `public AddSnap() : System.Void`  

```csharp
public System.Void AddSnap();
```

- `public AddTemp(Unity.Entities.Entity prefab, Game.Objects.Transform transform) : System.Void`  

```csharp
public System.Void AddTemp(Unity.Entities.Entity prefab, Game.Objects.Transform transform);
```

- `public Remove(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void Remove(Unity.Entities.Entity entity);
```

- `public Remove(Game.Effects.SourceInfo sourceInfo) : System.Void`  

```csharp
public System.Void Remove(Game.Effects.SourceInfo sourceInfo);
```

- `public WrongPrefab(Game.Effects.SourceInfo sourceInfo) : System.Void`  

```csharp
public System.Void WrongPrefab(Game.Effects.SourceInfo sourceInfo);
```


