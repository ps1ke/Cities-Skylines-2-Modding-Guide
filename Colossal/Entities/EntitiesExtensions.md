# Colossal.Entities.EntitiesExtensions

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Entities`  

**Type:** class static public  

**Base:** `System.Object`  

**Attributes:** `Extension`  

## Code

```csharp
public static class EntitiesExtensions
{
    public static System.Boolean HasEnabledBuffer<T>(Unity.Entities.BufferLookup<T> bufferLookup, Unity.Entities.Entity entity);
    public static System.Boolean HasEnabledComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public static System.Boolean HasEnabledComponent<T>(Unity.Entities.ComponentLookup<T> componentLookup, Unity.Entities.Entity entity);
    public static System.Boolean TryGetBuffer<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
    public static System.Boolean TryGetComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component);
    public static System.Boolean TryGetEnabledBuffer<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
    public static System.Boolean TryGetEnabledBuffer<T>(Unity.Entities.BufferLookup<T> bufferLookup, Unity.Entities.Entity entity, DynamicBuffer`1& buffer);
    public static System.Boolean TryGetEnabledComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component);
    public static System.Boolean TryGetEnabledComponent<T>(Unity.Entities.ComponentLookup<T> componentLookup, Unity.Entities.Entity entity, T& component);
    public static System.Boolean TryGetSharedComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component);
}
```


## Methods

- `public static HasEnabledBuffer<T>(Unity.Entities.BufferLookup<T> bufferLookup, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public static System.Boolean HasEnabledBuffer<T>(Unity.Entities.BufferLookup<T> bufferLookup, Unity.Entities.Entity entity);
```

- `public static HasEnabledComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public static System.Boolean HasEnabledComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public static HasEnabledComponent<T>(Unity.Entities.ComponentLookup<T> componentLookup, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public static System.Boolean HasEnabledComponent<T>(Unity.Entities.ComponentLookup<T> componentLookup, Unity.Entities.Entity entity);
```

- `public static TryGetBuffer<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Boolean isReadOnly, DynamicBuffer`1& buffer) : System.Boolean`  

```csharp
public static System.Boolean TryGetBuffer<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
```

- `public static TryGetComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component) : System.Boolean`  

```csharp
public static System.Boolean TryGetComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component);
```

- `public static TryGetEnabledBuffer<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Boolean isReadOnly, DynamicBuffer`1& buffer) : System.Boolean`  

```csharp
public static System.Boolean TryGetEnabledBuffer<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Boolean isReadOnly, DynamicBuffer`1& buffer);
```

- `public static TryGetEnabledBuffer<T>(Unity.Entities.BufferLookup<T> bufferLookup, Unity.Entities.Entity entity, DynamicBuffer`1& buffer) : System.Boolean`  

```csharp
public static System.Boolean TryGetEnabledBuffer<T>(Unity.Entities.BufferLookup<T> bufferLookup, Unity.Entities.Entity entity, DynamicBuffer`1& buffer);
```

- `public static TryGetEnabledComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component) : System.Boolean`  

```csharp
public static System.Boolean TryGetEnabledComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component);
```

- `public static TryGetEnabledComponent<T>(Unity.Entities.ComponentLookup<T> componentLookup, Unity.Entities.Entity entity, T& component) : System.Boolean`  

```csharp
public static System.Boolean TryGetEnabledComponent<T>(Unity.Entities.ComponentLookup<T> componentLookup, Unity.Entities.Entity entity, T& component);
```

- `public static TryGetSharedComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component) : System.Boolean`  

```csharp
public static System.Boolean TryGetSharedComponent<T>(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, T& component);
```


