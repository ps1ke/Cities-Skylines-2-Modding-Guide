# PDX.SDK.Contracts.Service.Mods.Models.ForumPost

**Assembly:** `PDX.SDK`  
**Namespace:** `PDX.SDK.Contracts.Service.Mods.Models`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class ForumPost
{
    private System.String <Username>k__BackingField;
    private System.Int32 <UserId>k__BackingField;
    private System.String <UserTitle>k__BackingField;
    private System.String <Url>k__BackingField;
    private System.Int32 <PostId>k__BackingField;
    private System.String <Message>k__BackingField;
    private System.DateTime <Created>k__BackingField;
    private System.String <Avatar>k__BackingField;
    private System.Boolean <MessageTooLong>k__BackingField;

    public System.String Username { get; set; }
    public System.Int32 UserId { get; set; }
    public System.String UserTitle { get; set; }
    public System.String Url { get; set; }
    public System.Int32 PostId { get; set; }
    public System.String Message { get; set; }
    public System.DateTime Created { get; set; }
    public System.String Avatar { get; set; }
    public System.Boolean MessageTooLong { get; set; }

    public ForumPost();

    public System.Boolean HasIdenticalAttributes(PDX.SDK.Contracts.Service.Mods.Models.ForumPost post);
}
```


## Fields

- `private System.String <Username>k__BackingField`  

```csharp
private System.String <Username>k__BackingField;
```

- `private System.Int32 <UserId>k__BackingField`  

```csharp
private System.Int32 <UserId>k__BackingField;
```

- `private System.String <UserTitle>k__BackingField`  

```csharp
private System.String <UserTitle>k__BackingField;
```

- `private System.String <Url>k__BackingField`  

```csharp
private System.String <Url>k__BackingField;
```

- `private System.Int32 <PostId>k__BackingField`  

```csharp
private System.Int32 <PostId>k__BackingField;
```

- `private System.String <Message>k__BackingField`  

```csharp
private System.String <Message>k__BackingField;
```

- `private System.DateTime <Created>k__BackingField`  

```csharp
private System.DateTime <Created>k__BackingField;
```

- `private System.String <Avatar>k__BackingField`  

```csharp
private System.String <Avatar>k__BackingField;
```

- `private System.Boolean <MessageTooLong>k__BackingField`  

```csharp
private System.Boolean <MessageTooLong>k__BackingField;
```


## Properties

- `public System.String Username { get; set }`  

```csharp
public System.String Username { get; set; }
```

- `public System.Int32 UserId { get; set }`  

```csharp
public System.Int32 UserId { get; set; }
```

- `public System.String UserTitle { get; set }`  

```csharp
public System.String UserTitle { get; set; }
```

- `public System.String Url { get; set }`  

```csharp
public System.String Url { get; set; }
```

- `public System.Int32 PostId { get; set }`  

```csharp
public System.Int32 PostId { get; set; }
```

- `public System.String Message { get; set }`  

```csharp
public System.String Message { get; set; }
```

- `public System.DateTime Created { get; set }`  

```csharp
public System.DateTime Created { get; set; }
```

- `public System.String Avatar { get; set }`  

```csharp
public System.String Avatar { get; set; }
```

- `public System.Boolean MessageTooLong { get; set }`  

```csharp
public System.Boolean MessageTooLong { get; set; }
```


## Constructors

- `public ForumPost()`  

```csharp
public ForumPost();
```


## Methods

- `public HasIdenticalAttributes(PDX.SDK.Contracts.Service.Mods.Models.ForumPost post) : System.Boolean`  

```csharp
public System.Boolean HasIdenticalAttributes(PDX.SDK.Contracts.Service.Mods.Models.ForumPost post);
```


