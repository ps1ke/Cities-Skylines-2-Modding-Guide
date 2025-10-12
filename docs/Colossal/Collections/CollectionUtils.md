# Colossal.Collections.CollectionUtils

**Assembly:** `Colossal.Collections`  
**Namespace:** `Colossal.Collections`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Methods

- `public static Add<T>(Unity.Entities.DynamicBuffer<T> destination, Unity.Entities.DynamicBuffer<T> source) : System.Void`  
- `public static AliasManagedArrayAsNativeArray<T>(T[] arr) : Unity.Collections.NativeArray<T>`  
- `public static ContainsValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Boolean`  
- `public static CopySafe<T>(Unity.Collections.NativeArray<T> src, Unity.Collections.NativeArray<T> dst) : System.Void`  
- `public static ElementAt<T>(Unity.Collections.NativeArray<T> array, System.Int32 index) : T&`  
- `public static Fill<T>(Unity.Collections.NativeArray<T> array, T value) : System.Void`  
- `public static Insert<T>(Unity.Collections.NativeList<T> list, System.Int32 index, T value) : System.Void`  
- `public static Remove<T>(Unity.Collections.NativeList<T> list, System.Int32 index) : System.Void`  
- `public static RemoveMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue value) : System.Void`  
- `public static RemoveValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Boolean`  
- `public static RemoveValueSwapBack<T>(Unity.Collections.NativeList<T> list, T value) : System.Boolean`  
- `public static RemoveValueSwapBack<T>(StackList`1& list, T value) : System.Boolean`  
- `public static ReplaceMultiHashMapValue<TKey, TValue>(Unity.Collections.NativeParallelMultiHashMap<TKey, TValue> map, TKey key, TValue oldValue, TValue newValue) : System.Void`  
- `public static Replenish<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Void`  
- `public static ResizeInitialized<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 size, T value = null) : System.Void`  
- `public static Reverse<T>(Unity.Collections.NativeArray<T> buffer) : System.Void`  
- `public static ToArray<T>(Unity.Collections.NativeQueue<T> queue, Unity.Collections.Allocator allocator) : Unity.Collections.NativeArray<T>`  
- `public static TryAddUniqueValue<T>(Unity.Entities.DynamicBuffer<T> buffer, T value) : System.Boolean`  
- `public static TryAddUniqueValue<T>(Unity.Collections.NativeList<T> buffer, T value) : System.Boolean`  
- `public static TryGet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T& value) : System.Boolean`  
- `public static TryGet<T>(Unity.Entities.DynamicBuffer<T> buffer, System.Int32 index, T& value) : System.Boolean`  
- `public static TryGet<T>(Unity.Entities.BufferAccessor<T> bufferAccessor, System.Int32 index, DynamicBuffer`1& value) : System.Boolean`  
- `public static TrySet<T>(Unity.Collections.NativeArray<T> buffer, System.Int32 index, T value) : System.Boolean`  
- `public static ValueAsRef<T>(Unity.Collections.NativeReference<T> container) : T&`  

