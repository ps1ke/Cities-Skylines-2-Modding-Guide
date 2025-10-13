# Game.UI.ImageSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ImageSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private static const System.String kPlaceholderIcon;
    private static const System.String kCitizenIcon;
    private static const System.String kTouristIcon;
    private static const System.String kCommuterIcon;
    private static const System.String kAnimalIcon;
    private static const System.String kPetIcon;
    private static const System.String kHealthcareIcon;
    private static const System.String kDeathcareIcon;
    private static const System.String kPoliceIcon;
    private static const System.String kGarbageIcon;
    private static const System.String kFireIcon;
    private static const System.String kPostIcon;
    private static const System.String kDeliveryIcon;

    public System.String placeholderIcon { get; }

    public ImageSystem();

    public System.String GetGroupIcon(Unity.Entities.Entity prefabEntity);
    public static System.String GetIcon(Game.Prefabs.PrefabBase prefab);
    public System.String GetIconOrGroupIcon(Unity.Entities.Entity prefabEntity);
    public System.String GetInstanceIcon(Unity.Entities.Entity instanceEntity);
    public System.String GetInstanceIcon(Unity.Entities.Entity instanceEntity, Unity.Entities.Entity prefabEntity);
    public System.String GetThumbnail(Unity.Entities.Entity prefabEntity);
    public static System.String GetThumbnail(Game.Prefabs.PrefabBase prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private static const System.String kPlaceholderIcon`  

```csharp
private static const System.String kPlaceholderIcon;
```

- `private static const System.String kCitizenIcon`  

```csharp
private static const System.String kCitizenIcon;
```

- `private static const System.String kTouristIcon`  

```csharp
private static const System.String kTouristIcon;
```

- `private static const System.String kCommuterIcon`  

```csharp
private static const System.String kCommuterIcon;
```

- `private static const System.String kAnimalIcon`  

```csharp
private static const System.String kAnimalIcon;
```

- `private static const System.String kPetIcon`  

```csharp
private static const System.String kPetIcon;
```

- `private static const System.String kHealthcareIcon`  

```csharp
private static const System.String kHealthcareIcon;
```

- `private static const System.String kDeathcareIcon`  

```csharp
private static const System.String kDeathcareIcon;
```

- `private static const System.String kPoliceIcon`  

```csharp
private static const System.String kPoliceIcon;
```

- `private static const System.String kGarbageIcon`  

```csharp
private static const System.String kGarbageIcon;
```

- `private static const System.String kFireIcon`  

```csharp
private static const System.String kFireIcon;
```

- `private static const System.String kPostIcon`  

```csharp
private static const System.String kPostIcon;
```

- `private static const System.String kDeliveryIcon`  

```csharp
private static const System.String kDeliveryIcon;
```


## Properties

- `public System.String placeholderIcon { get }`  

```csharp
public System.String placeholderIcon { get; }
```


## Constructors

- `public ImageSystem()`  

```csharp
public ImageSystem();
```


## Methods

- `public GetGroupIcon(Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
public System.String GetGroupIcon(Unity.Entities.Entity prefabEntity);
```

- `public static GetIcon(Game.Prefabs.PrefabBase prefab) : System.String`  

```csharp
public static System.String GetIcon(Game.Prefabs.PrefabBase prefab);
```

- `public GetIconOrGroupIcon(Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
public System.String GetIconOrGroupIcon(Unity.Entities.Entity prefabEntity);
```

- `public GetInstanceIcon(Unity.Entities.Entity instanceEntity) : System.String`  

```csharp
public System.String GetInstanceIcon(Unity.Entities.Entity instanceEntity);
```

- `public GetInstanceIcon(Unity.Entities.Entity instanceEntity, Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
public System.String GetInstanceIcon(Unity.Entities.Entity instanceEntity, Unity.Entities.Entity prefabEntity);
```

- `public GetThumbnail(Unity.Entities.Entity prefabEntity) : System.String`  

```csharp
public System.String GetThumbnail(Unity.Entities.Entity prefabEntity);
```

- `public static GetThumbnail(Game.Prefabs.PrefabBase prefab) : System.String`  

```csharp
public static System.String GetThumbnail(Game.Prefabs.PrefabBase prefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


