# Colossal.FileSystem.WatcherCapabilities

**Assembly:** `Colossal.IO`  
**Namespace:** `Colossal.FileSystem`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class WatcherCapabilities
{
    private System.Boolean <canDetectDirectoryCreateEvents>k__BackingField;
    private System.Boolean <canDetectDirectoryDeleteEvents>k__BackingField;
    private System.Boolean <canDetectDirectoryRenameEvents>k__BackingField;
    private System.Boolean <canDetectFileCreateEvents>k__BackingField;
    private System.Boolean <canDetectFileChangeEvents>k__BackingField;
    private System.Boolean <canDetectFileDeleteEvents>k__BackingField;
    private System.Boolean <canDetectFileRenameEvents>k__BackingField;
    private System.Int32 <pollFrequency>k__BackingField;

    public System.Boolean continuousPolling { get; }
    public System.Boolean canDetectDirectoryCreateEvents { get; private set; }
    public System.Boolean canDetectDirectoryDeleteEvents { get; private set; }
    public System.Boolean canDetectDirectoryRenameEvents { get; private set; }
    public System.Boolean canDetectFileCreateEvents { get; private set; }
    public System.Boolean canDetectFileChangeEvents { get; private set; }
    public System.Boolean canDetectFileDeleteEvents { get; private set; }
    public System.Boolean canDetectFileRenameEvents { get; private set; }
    public System.Int32 pollFrequency { get; private set; }

    public WatcherCapabilities(System.Boolean canDetectDirectoryCreate, System.Boolean canDetectDirectoryDelete, System.Boolean canDetectDirectoryRename, System.Boolean canDetectFileCreate, System.Boolean canDetectFileChange, System.Boolean canDetectFileDelete, System.Boolean canDetectFileRename);

    public System.Void SetPollFrequencyTo(System.Int32 milliseconds);
}
```


## Fields

- `private System.Boolean <canDetectDirectoryCreateEvents>k__BackingField`  

```csharp
private System.Boolean <canDetectDirectoryCreateEvents>k__BackingField;
```

- `private System.Boolean <canDetectDirectoryDeleteEvents>k__BackingField`  

```csharp
private System.Boolean <canDetectDirectoryDeleteEvents>k__BackingField;
```

- `private System.Boolean <canDetectDirectoryRenameEvents>k__BackingField`  

```csharp
private System.Boolean <canDetectDirectoryRenameEvents>k__BackingField;
```

- `private System.Boolean <canDetectFileCreateEvents>k__BackingField`  

```csharp
private System.Boolean <canDetectFileCreateEvents>k__BackingField;
```

- `private System.Boolean <canDetectFileChangeEvents>k__BackingField`  

```csharp
private System.Boolean <canDetectFileChangeEvents>k__BackingField;
```

- `private System.Boolean <canDetectFileDeleteEvents>k__BackingField`  

```csharp
private System.Boolean <canDetectFileDeleteEvents>k__BackingField;
```

- `private System.Boolean <canDetectFileRenameEvents>k__BackingField`  

```csharp
private System.Boolean <canDetectFileRenameEvents>k__BackingField;
```

- `private System.Int32 <pollFrequency>k__BackingField`  

```csharp
private System.Int32 <pollFrequency>k__BackingField;
```


## Properties

- `public System.Boolean continuousPolling { get }`  

```csharp
public System.Boolean continuousPolling { get; }
```

- `public System.Boolean canDetectDirectoryCreateEvents { get; private set }`  

```csharp
public System.Boolean canDetectDirectoryCreateEvents { get; private set; }
```

- `public System.Boolean canDetectDirectoryDeleteEvents { get; private set }`  

```csharp
public System.Boolean canDetectDirectoryDeleteEvents { get; private set; }
```

- `public System.Boolean canDetectDirectoryRenameEvents { get; private set }`  

```csharp
public System.Boolean canDetectDirectoryRenameEvents { get; private set; }
```

- `public System.Boolean canDetectFileCreateEvents { get; private set }`  

```csharp
public System.Boolean canDetectFileCreateEvents { get; private set; }
```

- `public System.Boolean canDetectFileChangeEvents { get; private set }`  

```csharp
public System.Boolean canDetectFileChangeEvents { get; private set; }
```

- `public System.Boolean canDetectFileDeleteEvents { get; private set }`  

```csharp
public System.Boolean canDetectFileDeleteEvents { get; private set; }
```

- `public System.Boolean canDetectFileRenameEvents { get; private set }`  

```csharp
public System.Boolean canDetectFileRenameEvents { get; private set; }
```

- `public System.Int32 pollFrequency { get; private set }`  

```csharp
public System.Int32 pollFrequency { get; private set; }
```


## Constructors

- `public WatcherCapabilities(System.Boolean canDetectDirectoryCreate, System.Boolean canDetectDirectoryDelete, System.Boolean canDetectDirectoryRename, System.Boolean canDetectFileCreate, System.Boolean canDetectFileChange, System.Boolean canDetectFileDelete, System.Boolean canDetectFileRename)`  

```csharp
public WatcherCapabilities(System.Boolean canDetectDirectoryCreate, System.Boolean canDetectDirectoryDelete, System.Boolean canDetectDirectoryRename, System.Boolean canDetectFileCreate, System.Boolean canDetectFileChange, System.Boolean canDetectFileDelete, System.Boolean canDetectFileRename);
```


## Methods

- `public SetPollFrequencyTo(System.Int32 milliseconds) : System.Void`  

```csharp
public System.Void SetPollFrequencyTo(System.Int32 milliseconds);
```


