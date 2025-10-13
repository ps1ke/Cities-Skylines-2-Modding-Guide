# Colossal.Collections.CollectionUtils

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class CollectionUtils
{
    public static System.Void Add<T>(Unity.Entities.DynamicBuffer<T> destination, Unity.Entities.DynamicBuffer<T> source);
    public static Unity.Collections.NativeArray<T> AliasManagedArrayAsNativeArray<T>(T[] arr);
    public static System.Boolean ContainsValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
    public static System.Void CopySafe<T>(Unity.Collections.NativeArray<T> src, Unity.Collections.NativeArray<T> dst);
    public static T& ElementAt<T>(Unity.Collections.NativeArray<T> array, System.Int32 index);
    public static System.Void Fill<T>(Unity.Collections.NativeArray<T> array, T value);
    public static System.Void Insert<T>(Unity.Collections.NativeList<T> list, System.Int32 index, T value);
    public static System.Void Remove<T>(Unity.Collections.NativeList<T> list, System.Int32 index);
    public static System.Void RemoveMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue value);
    public static System.Boolean RemoveValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
    public static System.Boolean RemoveValueSwapBack<T>(Unity.Collections.NativeList<T> list, T value);
    public static System.Boolean RemoveValueSwapBack<T>(StackList`1& list, T value);
    public static System.Void ReplaceMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue oldValue, TValue newValue);
    public static System.Void Replenish<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
    public static System.Void ResizeInitialized<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 size, T value);
    public static System.Void Reverse<T>(Unity.Collections.NativeArray<T> buffer);
    public static Unity.Collections.NativeArray<T> ToArray<T>(Unity.Collections.NativeQueue<T> queue, Unity.Collections.Allocator allocator);
    public static System.Boolean TryAddUniqueValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
    public static System.Boolean TryAddUniqueValue<T>(Unity.Collections.NativeList<T> buffer, T value);
    public static System.Boolean TryGet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T& value);
    public static System.Boolean TryGet<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 index, T& value);
    public static System.Boolean TryGet<T>(Unity.Entities.BufferAccessor<T> bufferAccessor, System.Int32 index, DynamicBuffer`1& value);
    public static System.Boolean TrySet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T value);
    public static T& ValueAsRef<T>(Unity.Collections.NativeReference<T> container);
}
```


## Methods

- `public static Add<T>(Unity.Entities.DynamicBuffer<T> destination, Unity.Entities.DynamicBuffer<T> source) : System.Void`  

```csharp
public static System.Void Add<T>(Unity.Entities.DynamicBuffer<T> destination, Unity.Entities.DynamicBuffer<T> source);
```

- `public static AliasManagedArrayAsNativeArray<T>(T[] arr) : Unity.Collections.NativeArray<T>`  

```csharp
public static Unity.Collections.NativeArray<T> AliasManagedArrayAsNativeArray<T>(T[] arr);
```

- `public static ContainsValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Boolean`  

```csharp
public static System.Boolean ContainsValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
```

- `public static CopySafe<T>(Unity.Collections.NativeArray<T> src, Unity.Collections.NativeArray<T> dst) : System.Void`  

```csharp
public static System.Void CopySafe<T>(Unity.Collections.NativeArray<T> src, Unity.Collections.NativeArray<T> dst);
```

- `public static ElementAt<T>(Unity.Collections.NativeArray<T> array, System.Int32 index) : T&`  

```csharp
public static T& ElementAt<T>(Unity.Collections.NativeArray<T> array, System.Int32 index);
```

- `public static Fill<T>(Unity.Collections.NativeArray<T> array, T value) : System.Void`  

```csharp
public static System.Void Fill<T>(Unity.Collections.NativeArray<T> array, T value);
```

- `public static Insert<T>(Unity.Collections.NativeList<T> list, System.Int32 index, T value) : System.Void`  

```csharp
public static System.Void Insert<T>(Unity.Collections.NativeList<T> list, System.Int32 index, T value);
```

- `public static Remove<T>(Unity.Collections.NativeList<T> list, System.Int32 index) : System.Void`  

```csharp
public static System.Void Remove<T>(Unity.Collections.NativeList<T> list, System.Int32 index);
```

- `public static RemoveMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue value) : System.Void`  

```csharp
public static System.Void RemoveMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue value);
```

- `public static RemoveValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Boolean`  

```csharp
public static System.Boolean RemoveValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
```

- `public static RemoveValueSwapBack<T>(Unity.Collections.NativeList<T> list, T value) : System.Boolean`  

```csharp
public static System.Boolean RemoveValueSwapBack<T>(Unity.Collections.NativeList<T> list, T value);
```

- `public static RemoveValueSwapBack<T>(StackList`1& list, T value) : System.Boolean`  

```csharp
public static System.Boolean RemoveValueSwapBack<T>(StackList`1& list, T value);
```

- `public static ReplaceMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue oldValue, TValue newValue) : System.Void`  

```csharp
public static System.Void ReplaceMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue oldValue, TValue newValue);
```

- `public static Replenish<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Void`  

```csharp
public static System.Void Replenish<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
```

- `public static ResizeInitialized<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 size, T value = null) : System.Void`  

```csharp
public static System.Void ResizeInitialized<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 size, T value);
```

- `public static Reverse<T>(Unity.Collections.NativeArray<T> buffer) : System.Void`  

```csharp
public static System.Void Reverse<T>(Unity.Collections.NativeArray<T> buffer);
```

- `public static ToArray<T>(Unity.Collections.NativeQueue<T> queue, Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<T>`  

```csharp
public static Unity.Collections.NativeArray<T> ToArray<T>(Unity.Collections.NativeQueue<T> queue, Unity.Collections.Allocator allocator);
```

- `public static TryAddUniqueValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Boolean`  

```csharp
public static System.Boolean TryAddUniqueValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value);
```

- `public static TryAddUniqueValue<T>(Unity.Collections.NativeList<T> buffer, T value) : System.Boolean`  

```csharp
public static System.Boolean TryAddUniqueValue<T>(Unity.Collections.NativeList<T> buffer, T value);
```

- `public static TryGet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T& value) : System.Boolean`  

```csharp
public static System.Boolean TryGet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T& value);
```

- `public static TryGet<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 index, T& value) : System.Boolean`  

```csharp
public static System.Boolean TryGet<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 index, T& value);
```

- `public static TryGet<T>(Unity.Entities.BufferAccessor<T> bufferAccessor, System.Int32 index, DynamicBuffer`1& value) : System.Boolean`  

```csharp
public static System.Boolean TryGet<T>(Unity.Entities.BufferAccessor<T> bufferAccessor, System.Int32 index, DynamicBuffer`1& value);
```

- `public static TrySet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T value) : System.Boolean`  

```csharp
public static System.Boolean TrySet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T value);
```

- `public static ValueAsRef<T>(Unity.Collections.NativeReference<T> container) : T&`  

```csharp
public static T& ValueAsRef<T>(Unity.Collections.NativeReference<T> container);
```


