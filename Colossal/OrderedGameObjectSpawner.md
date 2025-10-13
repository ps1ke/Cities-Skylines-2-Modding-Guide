# Colossal.OrderedGameObjectSpawner

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class OrderedGameObjectSpawner
{
    private System.String m_SectionName;
    private UnityEngine.Transform m_Section;
    private static System.Collections.Generic.Dictionary<System.String, Colossal.OrderedGameObjectSpawner> s_Instances;

    public OrderedGameObjectSpawner(System.String sectionName);

    public UnityEngine.GameObject Create(System.String name);
    public static Colossal.OrderedGameObjectSpawner Get(System.String sectionName);
}
```


## Fields

- `private System.String m_SectionName`  

```csharp
private System.String m_SectionName;
```

- `private UnityEngine.Transform m_Section`  

```csharp
private UnityEngine.Transform m_Section;
```

- `private static System.Collections.Generic.Dictionary<System.String, Colossal.OrderedGameObjectSpawner> s_Instances`  

```csharp
private static System.Collections.Generic.Dictionary<System.String, Colossal.OrderedGameObjectSpawner> s_Instances;
```


## Constructors

- `public OrderedGameObjectSpawner(System.String sectionName)`  

```csharp
public OrderedGameObjectSpawner(System.String sectionName);
```


## Methods

- `public Create(System.String name) : UnityEngine.GameObject`  

```csharp
public UnityEngine.GameObject Create(System.String name);
```

- `public static Get(System.String sectionName) : Colossal.OrderedGameObjectSpawner`  

```csharp
public static Colossal.OrderedGameObjectSpawner Get(System.String sectionName);
```


