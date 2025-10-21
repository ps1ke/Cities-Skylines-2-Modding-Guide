# Game.Net.EdgeIterator

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct EdgeIterator
{
    private Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_Edges;
    private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
    private Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    private Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_HiddenData;
    private Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> m_Buffer;
    private System.Int32 m_Iterator;
    private Unity.Entities.Entity m_Node;
    private Unity.Entities.Entity m_Edge;
    private Unity.Entities.Entity m_OriginalEdge;
    private System.Boolean m_Permanent;
    private System.Boolean m_Delete;
    private System.Boolean m_Middles;

    public EdgeIterator(Unity.Entities.Entity edge, Unity.Entities.Entity node, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> edges, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.ComponentLookup<Game.Tools.Temp> tempData, Unity.Entities.ComponentLookup<Game.Tools.Hidden> hiddenData, System.Boolean includeMiddleConnections);

    public System.Void AddSorted(Unity.Entities.ComponentLookup`1[[Game.Net.BuildOrder, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildOrderData, Colossal.Collections.StackList`1[[Game.Net.EdgeIteratorValueSorted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& list);
    private System.Boolean GetDelete(Unity.Entities.Entity entity);
    private System.Boolean GetDelete(Unity.Entities.Entity entity, Unity.Entities.Entity& original);
    public System.Int32 GetMaxCount();
    public System.Boolean GetNext(Game.Net.EdgeIteratorValue& value);
}
```


## Fields

- `private Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_Edges`  

```csharp
private Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_Edges;
```

- `private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
```

- `private Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `private Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_HiddenData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_HiddenData;
```

- `private Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> m_Buffer`  

```csharp
private Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> m_Buffer;
```

- `private System.Int32 m_Iterator`  

```csharp
private System.Int32 m_Iterator;
```

- `private Unity.Entities.Entity m_Node`  

```csharp
private Unity.Entities.Entity m_Node;
```

- `private Unity.Entities.Entity m_Edge`  

```csharp
private Unity.Entities.Entity m_Edge;
```

- `private Unity.Entities.Entity m_OriginalEdge`  

```csharp
private Unity.Entities.Entity m_OriginalEdge;
```

- `private System.Boolean m_Permanent`  

```csharp
private System.Boolean m_Permanent;
```

- `private System.Boolean m_Delete`  

```csharp
private System.Boolean m_Delete;
```

- `private System.Boolean m_Middles`  

```csharp
private System.Boolean m_Middles;
```


## Constructors

- `public EdgeIterator(Unity.Entities.Entity edge, Unity.Entities.Entity node, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> edges, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.ComponentLookup<Game.Tools.Temp> tempData, Unity.Entities.ComponentLookup<Game.Tools.Hidden> hiddenData, System.Boolean includeMiddleConnections = False)`  

```csharp
public EdgeIterator(Unity.Entities.Entity edge, Unity.Entities.Entity node, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> edges, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.ComponentLookup<Game.Tools.Temp> tempData, Unity.Entities.ComponentLookup<Game.Tools.Hidden> hiddenData, System.Boolean includeMiddleConnections);
```


## Methods

- `public AddSorted(Unity.Entities.ComponentLookup`1[[Game.Net.BuildOrder, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildOrderData, Colossal.Collections.StackList`1[[Game.Net.EdgeIteratorValueSorted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& list) : System.Void`  

```csharp
public System.Void AddSorted(Unity.Entities.ComponentLookup`1[[Game.Net.BuildOrder, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildOrderData, Colossal.Collections.StackList`1[[Game.Net.EdgeIteratorValueSorted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& list);
```

- `private GetDelete(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
private System.Boolean GetDelete(Unity.Entities.Entity entity);
```

- `private GetDelete(Unity.Entities.Entity entity, Unity.Entities.Entity& original) : System.Boolean`  

```csharp
private System.Boolean GetDelete(Unity.Entities.Entity entity, Unity.Entities.Entity& original);
```

- `public GetMaxCount() : System.Int32`  

```csharp
public System.Int32 GetMaxCount();
```

- `public GetNext(Game.Net.EdgeIteratorValue& value) : System.Boolean`  

```csharp
public System.Boolean GetNext(Game.Net.EdgeIteratorValue& value);
```


