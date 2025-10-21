# Game.UI.Editor.EditorAssetCategory

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class EditorAssetCategory
{
    private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_SubCategories;
    private System.String <id>k__BackingField;
    private System.String <path>k__BackingField;
    private Unity.Entities.EntityQuery <entityQuery>k__BackingField;
    private Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter <filter>k__BackingField;
    private System.Collections.Generic.HashSet<Unity.Entities.Entity> <exclude>k__BackingField;
    private System.Collections.Generic.List<Unity.Entities.Entity> <include>k__BackingField;
    private System.String <icon>k__BackingField;
    private System.Boolean <includeChildCategories>k__BackingField;
    private System.Boolean <defaultSelection>k__BackingField;
    public static readonly System.String kNameFormat;

    public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.EditorAssetCategory> subCategories { get; }
    public System.String id { get; set; }
    public System.String path { get; set; }
    public Unity.Entities.EntityQuery entityQuery { get; set; }
    public Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter filter { get; set; }
    private System.Collections.Generic.HashSet<Unity.Entities.Entity> exclude { private get; private set; }
    private System.Collections.Generic.List<Unity.Entities.Entity> include { private get; private set; }
    public System.String icon { get; set; }
    public System.Boolean includeChildCategories { get; set; }
    public System.Boolean defaultSelection { get; set; }

    public EditorAssetCategory();

    public System.Void AddEntity(Unity.Entities.Entity entity);
    public System.Void AddExclusion(Unity.Entities.Entity entity);
    public System.Void AddSubCategory(Game.UI.Editor.EditorAssetCategory category);
    private System.Boolean CheckFilters(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
    public System.Collections.Generic.IEnumerable<Unity.Entities.Entity> GetEntities(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType);
    public System.String GetLocalizationID();
    public System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> GetPrefabs(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType);
    public System.Boolean IsEmpty(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType);
    public Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory> ToHierarchyItem(System.Int32 level);
}
```


## Fields

- `private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_SubCategories`  

```csharp
private System.Collections.Generic.List<Game.UI.Editor.EditorAssetCategory> m_SubCategories;
```

- `private System.String <id>k__BackingField`  

```csharp
private System.String <id>k__BackingField;
```

- `private System.String <path>k__BackingField`  

```csharp
private System.String <path>k__BackingField;
```

- `private Unity.Entities.EntityQuery <entityQuery>k__BackingField`  

```csharp
private Unity.Entities.EntityQuery <entityQuery>k__BackingField;
```

- `private Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter <filter>k__BackingField`  

```csharp
private Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter <filter>k__BackingField;
```

- `private System.Collections.Generic.HashSet<Unity.Entities.Entity> <exclude>k__BackingField`  

```csharp
private System.Collections.Generic.HashSet<Unity.Entities.Entity> <exclude>k__BackingField;
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> <include>k__BackingField`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> <include>k__BackingField;
```

- `private System.String <icon>k__BackingField`  

```csharp
private System.String <icon>k__BackingField;
```

- `private System.Boolean <includeChildCategories>k__BackingField`  

```csharp
private System.Boolean <includeChildCategories>k__BackingField;
```

- `private System.Boolean <defaultSelection>k__BackingField`  

```csharp
private System.Boolean <defaultSelection>k__BackingField;
```

- `public static readonly System.String kNameFormat`  

```csharp
public static readonly System.String kNameFormat;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.EditorAssetCategory> subCategories { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.UI.Editor.EditorAssetCategory> subCategories { get; }
```

- `public System.String id { get; set }`  

```csharp
public System.String id { get; set; }
```

- `public System.String path { get; set }`  

```csharp
public System.String path { get; set; }
```

- `public Unity.Entities.EntityQuery entityQuery { get; set }`  

```csharp
public Unity.Entities.EntityQuery entityQuery { get; set; }
```

- `public Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter filter { get; set }`  

```csharp
public Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter filter { get; set; }
```

- `private System.Collections.Generic.HashSet<Unity.Entities.Entity> exclude { private get; private set }`  

```csharp
private System.Collections.Generic.HashSet<Unity.Entities.Entity> exclude { private get; private set; }
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> include { private get; private set }`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> include { private get; private set; }
```

- `public System.String icon { get; set }`  

```csharp
public System.String icon { get; set; }
```

- `public System.Boolean includeChildCategories { get; set }`  

```csharp
public System.Boolean includeChildCategories { get; set; }
```

- `public System.Boolean defaultSelection { get; set }`  

```csharp
public System.Boolean defaultSelection { get; set; }
```


## Constructors

- `public EditorAssetCategory()`  

```csharp
public EditorAssetCategory();
```


## Methods

- `public AddEntity(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void AddEntity(Unity.Entities.Entity entity);
```

- `public AddExclusion(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void AddExclusion(Unity.Entities.Entity entity);
```

- `public AddSubCategory(Game.UI.Editor.EditorAssetCategory category) : System.Void`  

```csharp
public System.Void AddSubCategory(Game.UI.Editor.EditorAssetCategory category);
```

- `private CheckFilters(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
private System.Boolean CheckFilters(Unity.Entities.Entity entity, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```

- `public GetEntities(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType) : System.Collections.Generic.IEnumerable<Unity.Entities.Entity>`  

```csharp
public System.Collections.Generic.IEnumerable<Unity.Entities.Entity> GetEntities(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType);
```

- `public GetLocalizationID() : System.String`  

```csharp
public System.String GetLocalizationID();
```

- `public GetPrefabs(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType) : System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase>`  

```csharp
public System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> GetPrefabs(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType);
```

- `public IsEmpty(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType) : System.Boolean`  

```csharp
public System.Boolean IsEmpty(Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem, Unity.Entities.EntityTypeHandle entityType);
```

- `public ToHierarchyItem(System.Int32 level = 0) : Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory>`  

```csharp
public Game.UI.Editor.HierarchyItem<Game.UI.Editor.EditorAssetCategory> ToHierarchyItem(System.Int32 level);
```


## Nested types

- `Game.UI.Editor.EditorAssetCategory+<GetEntities>d__42`  

