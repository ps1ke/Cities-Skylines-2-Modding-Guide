# Game.Input.ICustomComposite

**Assembly:** `Game`  
**Namespace:** `Game.Input`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ICustomComposite
{
    public static const System.Boolean kDefaultIsRebindable;
    public static const System.Boolean kDefaultIsModifiersRebindable;
    public static const System.Boolean kDefaultAllowModifiers;
    public static const System.Boolean kDefaultCanBeEmpty;
    public static const System.Boolean kDefaultDeveloperOnly;
    public static const System.Boolean kDefaultBuiltIn;
    public static const System.Boolean kDefaultIsDummy;
    public static const System.Boolean kDefaultIsHidden;
    public static const Game.Input.Mode kDefaultMode;
    public static const Game.Input.OptionGroupOverride kDefaultOptionGroupOverride;
    public static const Colossal.Platform kDefaultPlatform;

    public System.Boolean isRebindable { get; }
    public System.Boolean isModifiersRebindable { get; }
    public System.Boolean allowModifiers { get; }
    public System.Boolean canBeEmpty { get; }
    public System.Boolean developerOnly { get; }
    public Colossal.Platform platform { get; }
    public System.Boolean builtIn { get; }
    public System.Boolean isDummy { get; }
    public System.Boolean isHidden { get; }
    public Game.Input.Usages usages { get; }
    public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get; }
    public Game.Input.OptionGroupOverride optionGroupOverride { get; }
    public System.Guid linkedGuid { get; }
    public static Game.Input.Usages defaultUsages { get; }

}
```


## Fields

- `public static const System.Boolean kDefaultIsRebindable`  

```csharp
public static const System.Boolean kDefaultIsRebindable;
```

- `public static const System.Boolean kDefaultIsModifiersRebindable`  

```csharp
public static const System.Boolean kDefaultIsModifiersRebindable;
```

- `public static const System.Boolean kDefaultAllowModifiers`  

```csharp
public static const System.Boolean kDefaultAllowModifiers;
```

- `public static const System.Boolean kDefaultCanBeEmpty`  

```csharp
public static const System.Boolean kDefaultCanBeEmpty;
```

- `public static const System.Boolean kDefaultDeveloperOnly`  

```csharp
public static const System.Boolean kDefaultDeveloperOnly;
```

- `public static const System.Boolean kDefaultBuiltIn`  

```csharp
public static const System.Boolean kDefaultBuiltIn;
```

- `public static const System.Boolean kDefaultIsDummy`  

```csharp
public static const System.Boolean kDefaultIsDummy;
```

- `public static const System.Boolean kDefaultIsHidden`  

```csharp
public static const System.Boolean kDefaultIsHidden;
```

- `public static const Game.Input.Mode kDefaultMode`  

```csharp
public static const Game.Input.Mode kDefaultMode;
```

- `public static const Game.Input.OptionGroupOverride kDefaultOptionGroupOverride`  

```csharp
public static const Game.Input.OptionGroupOverride kDefaultOptionGroupOverride;
```

- `public static const Colossal.Platform kDefaultPlatform`  

```csharp
public static const Colossal.Platform kDefaultPlatform;
```


## Properties

- `public System.Boolean isRebindable { get }`  

```csharp
public System.Boolean isRebindable { get; }
```

- `public System.Boolean isModifiersRebindable { get }`  

```csharp
public System.Boolean isModifiersRebindable { get; }
```

- `public System.Boolean allowModifiers { get }`  

```csharp
public System.Boolean allowModifiers { get; }
```

- `public System.Boolean canBeEmpty { get }`  

```csharp
public System.Boolean canBeEmpty { get; }
```

- `public System.Boolean developerOnly { get }`  

```csharp
public System.Boolean developerOnly { get; }
```

- `public Colossal.Platform platform { get }`  

```csharp
public Colossal.Platform platform { get; }
```

- `public System.Boolean builtIn { get }`  

```csharp
public System.Boolean builtIn { get; }
```

- `public System.Boolean isDummy { get }`  

```csharp
public System.Boolean isDummy { get; }
```

- `public System.Boolean isHidden { get }`  

```csharp
public System.Boolean isHidden { get; }
```

- `public Game.Input.Usages usages { get }`  

```csharp
public Game.Input.Usages usages { get; }
```

- `public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get }`  

```csharp
public UnityEngine.InputSystem.Utilities.NameAndParameters parameters { get; }
```

- `public Game.Input.OptionGroupOverride optionGroupOverride { get }`  

```csharp
public Game.Input.OptionGroupOverride optionGroupOverride { get; }
```

- `public System.Guid linkedGuid { get }`  

```csharp
public System.Guid linkedGuid { get; }
```

- `public static Game.Input.Usages defaultUsages { get }`  

```csharp
public static Game.Input.Usages defaultUsages { get; }
```


