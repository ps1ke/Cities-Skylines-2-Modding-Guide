# Game.UI.InGame.EmploymentData

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct EmploymentData : Colossal.UI.Binding.IJsonWritable
{
    private readonly System.Int32 <uneducated>k__BackingField;
    private readonly System.Int32 <poorlyEducated>k__BackingField;
    private readonly System.Int32 <educated>k__BackingField;
    private readonly System.Int32 <wellEducated>k__BackingField;
    private readonly System.Int32 <highlyEducated>k__BackingField;
    private readonly System.Int32 <openPositions>k__BackingField;
    private readonly System.Int32 <total>k__BackingField;

    public System.Int32 uneducated { get; }
    public System.Int32 poorlyEducated { get; }
    public System.Int32 educated { get; }
    public System.Int32 wellEducated { get; }
    public System.Int32 highlyEducated { get; }
    public System.Int32 openPositions { get; }
    public System.Int32 total { get; }

    public EmploymentData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated, System.Int32 openPositions);

    public static Game.UI.InGame.EmploymentData GetEmployeesData(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 openPositions);
    public static Game.UI.InGame.EmploymentData GetWorkplacesData(System.Int32 maxWorkers, System.Int32 buildingLevel, Game.Prefabs.WorkplaceComplexity complexity);
    public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
}
```


## Fields

- `private readonly System.Int32 <uneducated>k__BackingField`  

```csharp
private readonly System.Int32 <uneducated>k__BackingField;
```

- `private readonly System.Int32 <poorlyEducated>k__BackingField`  

```csharp
private readonly System.Int32 <poorlyEducated>k__BackingField;
```

- `private readonly System.Int32 <educated>k__BackingField`  

```csharp
private readonly System.Int32 <educated>k__BackingField;
```

- `private readonly System.Int32 <wellEducated>k__BackingField`  

```csharp
private readonly System.Int32 <wellEducated>k__BackingField;
```

- `private readonly System.Int32 <highlyEducated>k__BackingField`  

```csharp
private readonly System.Int32 <highlyEducated>k__BackingField;
```

- `private readonly System.Int32 <openPositions>k__BackingField`  

```csharp
private readonly System.Int32 <openPositions>k__BackingField;
```

- `private readonly System.Int32 <total>k__BackingField`  

```csharp
private readonly System.Int32 <total>k__BackingField;
```


## Properties

- `public System.Int32 uneducated { get }`  

```csharp
public System.Int32 uneducated { get; }
```

- `public System.Int32 poorlyEducated { get }`  

```csharp
public System.Int32 poorlyEducated { get; }
```

- `public System.Int32 educated { get }`  

```csharp
public System.Int32 educated { get; }
```

- `public System.Int32 wellEducated { get }`  

```csharp
public System.Int32 wellEducated { get; }
```

- `public System.Int32 highlyEducated { get }`  

```csharp
public System.Int32 highlyEducated { get; }
```

- `public System.Int32 openPositions { get }`  

```csharp
public System.Int32 openPositions { get; }
```

- `public System.Int32 total { get }`  

```csharp
public System.Int32 total { get; }
```


## Constructors

- `public EmploymentData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated, System.Int32 openPositions)`  

```csharp
public EmploymentData(System.Int32 uneducated, System.Int32 poorlyEducated, System.Int32 educated, System.Int32 wellEducated, System.Int32 highlyEducated, System.Int32 openPositions);
```


## Methods

- `public static GetEmployeesData(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 openPositions) : Game.UI.InGame.EmploymentData`  

```csharp
public static Game.UI.InGame.EmploymentData GetEmployeesData(Unity.Entities.DynamicBuffer<Game.Companies.Employee> employees, System.Int32 openPositions);
```

- `public static GetWorkplacesData(System.Int32 maxWorkers, System.Int32 buildingLevel, Game.Prefabs.WorkplaceComplexity complexity) : Game.UI.InGame.EmploymentData`  

```csharp
public static Game.UI.InGame.EmploymentData GetWorkplacesData(System.Int32 maxWorkers, System.Int32 buildingLevel, Game.Prefabs.WorkplaceComplexity complexity);
```

- `public Write(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public System.Void Write(Colossal.UI.Binding.IJsonWriter writer);
```


