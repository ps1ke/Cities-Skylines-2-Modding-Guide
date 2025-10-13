# Game.UI.Tooltip.RaycastElectricityTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastElectricityTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Game.UI.Tooltip.IntTooltip m_Production;
    private Game.UI.Tooltip.IntTooltip m_TransformerCapacity;
    private Game.UI.Tooltip.IntTooltip m_Usage;
    private Game.UI.Tooltip.IntTooltip m_BatteryFlow;
    private Game.UI.Tooltip.IntTooltip m_BatteryCharge;
    private Game.UI.Tooltip.ProgressTooltip m_Consumption;
    private Game.UI.Tooltip.ProgressTooltip m_Flow;
    private Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle __TypeHandle;

    public RaycastElectricityTooltipSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition);
    private System.Void AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge);
    private System.Boolean HasBottleneck(Unity.Entities.Entity building);
    private System.Boolean IsInfomodeActivated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem`  

```csharp
private Game.Simulation.ElectricityFlowSystem m_ElectricityFlowSystem;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Production`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Production;
```

- `private Game.UI.Tooltip.IntTooltip m_TransformerCapacity`  

```csharp
private Game.UI.Tooltip.IntTooltip m_TransformerCapacity;
```

- `private Game.UI.Tooltip.IntTooltip m_Usage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Usage;
```

- `private Game.UI.Tooltip.IntTooltip m_BatteryFlow`  

```csharp
private Game.UI.Tooltip.IntTooltip m_BatteryFlow;
```

- `private Game.UI.Tooltip.IntTooltip m_BatteryCharge`  

```csharp
private Game.UI.Tooltip.IntTooltip m_BatteryCharge;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Consumption`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Consumption;
```

- `private Game.UI.Tooltip.ProgressTooltip m_Flow`  

```csharp
private Game.UI.Tooltip.ProgressTooltip m_Flow;
```

- `private Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RaycastElectricityTooltipSystem()`  

```csharp
[Preserve]
	public RaycastElectricityTooltipSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `private AddEdgeFlow(Unity.Entities.Entity edge, System.Single curvePosition) : System.Void`  

```csharp
private void AddEdgeFlow(Entity edge, float curvePosition)
	{
		ComponentLookup<ElectricityNodeConnection> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef);
		BufferLookup<ConnectedFlowEdge> flowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef);
		ComponentLookup<ElectricityFlowEdge> flowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ElectricityConsumer> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Building> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ElectricityBuildingConnection> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentLookup, ref base.CheckedStateRef);
		if (!base.EntityManager.TryGetComponent<Edge>(edge, out var component) || !componentLookup.TryGetComponent(edge, out var componentData) || !componentLookup.TryGetComponent(component.m_Start, out var componentData2) || !componentLookup.TryGetComponent(component.m_End, out var _) || !ElectricityGraphUtils.TryGetFlowEdge(componentData2.m_ElectricityNode, componentData.m_ElectricityNode, ref flowConnections, ref flowEdges, out ElectricityFlowEdge edge2))
		{
			return;
		}
		int num = math.max(1, edge2.m_Capacity);
		int num2 = edge2.m_Flow;
		if (base.EntityManager.TryGetBuffer(edge, isReadOnly: true, out DynamicBuffer<ConnectedNode> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				ConnectedNode connectedNode = buffer[i];
				if (connectedNode.m_CurvePosition < curvePosition && componentLookup.TryGetComponent(connectedNode.m_Node, out var componentData4) && ElectricityGraphUtils.TryGetFlowEdge(componentData4.m_ElectricityNode, componentData.m_ElectricityNode, ref flowConnections, ref flowEdges, out ElectricityFlowEdge edge3))
				{
					num2 += edge3.m_Flow;
				}
			}
		}
		if (ElectricityGraphUtils.TryGetFlowEdge(componentData.m_ElectricityNode, m_ElectricityFlowSystem.sinkNode, ref flowConnections, ref flowEdges, out ElectricityFlowEdge edge4) && base.EntityManager.TryGetBuffer(edge, isReadOnly: true, out DynamicBuffer<ConnectedBuilding> buffer2))
		{
			int totalSupply = edge4.m_Flow;
			int totalDemand = 0;
			for (int j = 0; j < buffer2.Length; j++)
			{
				ConnectedBuilding connectedBuilding = buffer2[j];
				if (!componentLookup4.HasComponent(connectedBuilding.m_Building) && componentLookup2.TryGetComponent(connectedBuilding.m_Building, out var componentData5))
				{
					totalDemand += componentData5.m_WantedConsumption;
				}
			}
			for (int k = 0; k < buffer2.Length; k++)
			{
				ConnectedBuilding connectedBuilding2 = buffer2[k];
				if (!componentLookup4.HasComponent(connectedBuilding2.m_Building) && componentLookup2.TryGetComponent(connectedBuilding2.m_Building, out var componentData6))
				{
					int num3 = FlowUtils.ConsumeFromTotal(componentData6.m_WantedConsumption, ref totalSupply, ref totalDemand);
					if (componentLookup3[connectedBuilding2.m_Building].m_CurvePosition < curvePosition)
					{
						num2 -= num3;
					}
				}
			}
		}
		m_Flow.value = math.abs(num2);
		m_Flow.max = num;
		AddMouseTooltip(m_Flow);
	}
```

- `private AddNodeFlow(Unity.Entities.Entity node, Unity.Entities.Entity edge) : System.Void`  

```csharp
private void AddNodeFlow(Entity node, Entity edge)
	{
		if (!base.EntityManager.TryGetComponent<ElectricityNodeConnection>(node, out var component) || !base.EntityManager.TryGetComponent<ElectricityNodeConnection>(edge, out var component2) || !base.EntityManager.TryGetBuffer(component.m_ElectricityNode, isReadOnly: true, out DynamicBuffer<ConnectedFlowEdge> buffer))
		{
			return;
		}
		int num = 0;
		int num2 = 0;
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity edge2 = buffer[i].m_Edge;
			ElectricityFlowEdge componentData = base.EntityManager.GetComponentData<ElectricityFlowEdge>(edge2);
			if (componentData.m_Start == component2.m_ElectricityNode || componentData.m_End == component2.m_ElectricityNode)
			{
				int num3 = math.abs(componentData.m_Flow);
				if (num3 > num || (num3 == num && componentData.m_Capacity > num2))
				{
					num = num3;
					num2 = componentData.m_Capacity;
				}
			}
		}
		if (num2 > 0)
		{
			m_Flow.value = num;
			m_Flow.max = num2;
			AddMouseTooltip(m_Flow);
		}
	}
```

- `private HasBottleneck(Unity.Entities.Entity building) : System.Boolean`  

```csharp
private bool HasBottleneck(Entity building)
	{
		if (base.EntityManager.TryGetComponent<ElectricityBuildingConnection>(building, out var component))
		{
			if (component.m_ProducerEdge != Entity.Null && base.EntityManager.GetComponentData<ElectricityFlowEdge>(component.m_ProducerEdge).isBottleneck)
			{
				return true;
			}
			if (component.m_TransformerNode != Entity.Null)
			{
				foreach (ConnectedFlowEdge item in base.EntityManager.GetBuffer<ConnectedFlowEdge>(component.m_TransformerNode, isReadOnly: true))
				{
					if (base.EntityManager.GetComponentData<ElectricityFlowEdge>(item.m_Edge).isBottleneck)
					{
						return true;
					}
				}
			}
		}
		return false;
	}
```

- `private IsInfomodeActivated() : System.Boolean`  

```csharp
private bool IsInfomodeActivated()
	{
		NativeArray<InfoviewNetStatusData> nativeArray = m_InfomodeQuery.ToComponentDataArray<InfoviewNetStatusData>(Allocator.Temp);
		try
		{
			foreach (InfoviewNetStatusData item in nativeArray)
			{
				if (item.m_Type == NetStatusType.LowVoltageFlow || item.m_Type == NetStatusType.HighVoltageFlow)
				{
					return true;
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_DefaultTool = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_ElectricityFlowSystem = base.World.GetOrCreateSystemManaged<ElectricityFlowSystem>();
		m_InfomodeQuery = GetEntityQuery(ComponentType.ReadOnly<InfomodeActive>(), ComponentType.ReadOnly<InfoviewNetStatusData>());
		RequireForUpdate(m_InfomodeQuery);
		m_Production = new IntTooltip
		{
			path = "electricityProduction",
			label = LocalizedString.Id("Tools.ELECTRICITY_PRODUCTION_LABEL"),
			unit = "power"
		};
		m_TransformerCapacity = new IntTooltip
		{
			path = "transformerCapacity",
			label = LocalizedString.Id("SelectedInfoPanel.ELECTRICITY_TRANSFORMER_CAPACITY"),
			unit = "power"
		};
		m_Usage = new IntTooltip
		{
			path = "electricityUsage",
			label = LocalizedString.Id("SelectedInfoPanel.ELECTRICITY_POWER_USAGE"),
			unit = "percentage"
		};
		m_BatteryFlow = new IntTooltip
		{
			path = "batteryFlow",
			label = LocalizedString.Id("Tools.BATTERY_FLOW"),
			unit = "power",
			signed = true
		};
		m_BatteryCharge = new IntTooltip
		{
			path = "batteryCharge",
			label = LocalizedString.Id("Tools.BATTERY_CHARGE"),
			unit = "percentage"
		};
		m_Consumption = new ProgressTooltip
		{
			path = "cElectricityConsumption",
			label = LocalizedString.Id("Tools.ELECTRICITY_CONSUMPTION_LABEL"),
			unit = "power",
			color = TooltipColor.Warning,
			omitMax = true
		};
		m_Flow = new ProgressTooltip
		{
			path = "electricityFlow",
			label = LocalizedString.Id("Tools.ELECTRICITY_FLOW_LABEL"),
			unit = "power"
		};
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		CompleteDependency();
		if (!IsInfomodeActivated() || m_ToolSystem.activeTool != m_DefaultTool || !m_ToolRaycastSystem.GetRaycastResult(out var result) || base.EntityManager.HasComponent<Destroyed>(result.m_Owner))
		{
			return;
		}
		if (base.EntityManager.HasComponent<Game.Net.UtilityLane>(result.m_Owner))
		{
			PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(result.m_Owner);
			if (base.EntityManager.TryGetComponent<UtilityLaneData>(componentData.m_Prefab, out var component) && base.EntityManager.TryGetComponent<EdgeMapping>(result.m_Owner, out var component2) && (component.m_UtilityTypes & (UtilityTypes.LowVoltageLine | UtilityTypes.HighVoltageLine)) != UtilityTypes.None)
			{
				Owner component3;
				if (component2.m_Parent1 != Entity.Null)
				{
					if (base.EntityManager.HasComponent<Edge>(component2.m_Parent1))
					{
						if (component2.m_Parent2 != Entity.Null)
						{
							if (result.m_Hit.m_CurvePosition < 0.5f)
							{
								float curvePosition = math.lerp(component2.m_CurveDelta1.x, component2.m_CurveDelta1.y, result.m_Hit.m_CurvePosition * 2f);
								AddEdgeFlow(component2.m_Parent1, curvePosition);
							}
							else
							{
								float curvePosition2 = math.lerp(component2.m_CurveDelta2.x, component2.m_CurveDelta2.y, result.m_Hit.m_CurvePosition * 2f - 1f);
								AddEdgeFlow(component2.m_Parent2, curvePosition2);
							}
						}
						else
						{
							float curvePosition3 = math.lerp(component2.m_CurveDelta1.x, component2.m_CurveDelta1.y, result.m_Hit.m_CurvePosition);
							AddEdgeFlow(component2.m_Parent1, curvePosition3);
						}
					}
					else
					{
						AddNodeFlow(component2.m_Parent1, component2.m_Parent2);
					}
				}
				else if (base.EntityManager.HasComponent<Game.Net.SecondaryLane>(result.m_Owner) && base.EntityManager.TryGetComponent<Owner>(result.m_Owner, out component3))
				{
					result.m_Owner = component3.m_Owner;
				}
			}
		}
		if (base.EntityManager.TryGetComponent<ElectricityProducer>(result.m_Owner, out var component4))
		{
			m_Production.value = component4.m_Capacity;
			AddMouseTooltip(m_Production);
			if (component4.m_Capacity > 0)
			{
				m_Usage.value = ((component4.m_LastProduction > 0) ? math.clamp(100 * component4.m_LastProduction / component4.m_Capacity, 1, 100) : 0);
				m_Usage.color = (HasBottleneck(result.m_Owner) ? TooltipColor.Warning : TooltipColor.Info);
				AddMouseTooltip(m_Usage);
			}
		}
		else if (base.EntityManager.HasComponent<Game.Buildings.Transformer>(result.m_Owner))
		{
			Game.Simulation.TransformerData transformerData = new Game.Simulation.TransformerData
			{
				m_Deleted = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ElectricityConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_NetNodes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityNodeConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityNodeConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityValveConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityValveConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FlowConnections = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Simulation_ConnectedFlowEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RO_ComponentLookup, ref base.CheckedStateRef)
			};
			transformerData.GetTransformerData(result.m_Owner, out var capacity, out var flow);
			m_TransformerCapacity.value = capacity;
			AddMouseTooltip(m_TransformerCapacity);
			if (capacity > 0)
			{
				m_Usage.value = ((flow != 0) ? math.clamp(100 * math.abs(flow) / capacity, 1, 100) : 0);
				m_Usage.color = (HasBottleneck(result.m_Owner) ? TooltipColor.Warning : TooltipColor.Info);
				AddMouseTooltip(m_Usage);
			}
		}
		if (base.EntityManager.TryGetComponent<Game.Buildings.Battery>(result.m_Owner, out var component5) && component5.m_Capacity > 0)
		{
			m_BatteryFlow.value = component5.m_LastFlow;
			m_BatteryCharge.value = 100 * component5.storedEnergyHours / component5.m_Capacity;
			m_BatteryCharge.color = ((component5.m_StoredEnergy <= 0) ? TooltipColor.Warning : TooltipColor.Info);
			AddMouseTooltip(m_BatteryFlow);
			AddMouseTooltip(m_BatteryCharge);
		}
		if (base.EntityManager.TryGetComponent<ElectricityConsumer>(result.m_Owner, out var component6))
		{
			m_Consumption.value = component6.m_FulfilledConsumption;
			m_Consumption.max = component6.m_WantedConsumption;
			m_Consumption.color = ((component6.m_FulfilledConsumption < component6.m_WantedConsumption) ? TooltipColor.Warning : TooltipColor.Info);
			AddMouseTooltip(m_Consumption);
		}
	}
```


## Nested types

- `Game.UI.Tooltip.RaycastElectricityTooltipSystem+TypeHandle`  

