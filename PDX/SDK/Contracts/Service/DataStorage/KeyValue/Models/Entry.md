# PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models.Entry

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.DataStorage.KeyValue.Models`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Entry
{
    private System.String <Key>k__BackingField;
    private System.String <Value>k__BackingField;
    private readonly System.String <Timestamp>k__BackingField;

    public System.String Key { get; set; }
    public System.String Value { get; set; }
    public System.String Timestamp { get; }

    public Entry(System.String key);
    public Entry(System.String key, System.String value);
    public Entry(System.String key, System.String value, System.String timestamp);

}
```


## Fields

- `private System.String <Key>k__BackingField`  

```csharp
private System.String <Key>k__BackingField;
```

- `private System.String <Value>k__BackingField`  

```csharp
private System.String <Value>k__BackingField;
```

- `private readonly System.String <Timestamp>k__BackingField`  

```csharp
private readonly System.String <Timestamp>k__BackingField;
```


## Properties

- `public System.String Key { get; set }`  

```csharp
public System.String Key { get; set; }
```

- `public System.String Value { get; set }`  

```csharp
public System.String Value { get; set; }
```

- `public System.String Timestamp { get }`  

```csharp
public System.String Timestamp { get; }
```


## Constructors

- `public Entry(System.String key)`  

```csharp
public Entry(System.String key);
```

- `public Entry(System.String key, System.String value)`  

```csharp
public Entry(System.String key, System.String value);
```

- `public Entry(System.String key, System.String value, System.String timestamp)`  

```csharp
public Entry(System.String key, System.String value, System.String timestamp);
```


