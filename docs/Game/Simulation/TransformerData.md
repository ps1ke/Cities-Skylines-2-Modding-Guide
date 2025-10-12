# Game.Simulation.TransformerData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Deleted> m_Deleted`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefs`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ElectricityConnectionData> m_ElectricityConnectionDatas`  
- `public Unity.Entities.BufferLookup<Game.Buildings.InstalledUpgrade> m_InstalledUpgrades`  
- `public Unity.Entities.BufferLookup<Game.Net.SubNet> m_SubNets`  
- `public Unity.Entities.ComponentLookup<Game.Net.Node> m_NetNodes`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityNodeConnection> m_ElectricityNodeConnections`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityValveConnection> m_ElectricityValveConnections`  
- `public Unity.Entities.BufferLookup<Game.Simulation.ConnectedFlowEdge> m_FlowConnections`  
- `public Unity.Entities.ComponentLookup<Game.Simulation.ElectricityFlowEdge> m_FlowEdges`  

## Methods

- `public GetTransformerData(Unity.Entities.Entity entity, System.Int32& capacity, System.Int32& flow) : System.Void`  
- `private ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Buildings.InstalledUpgrade> upgrades, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow) : System.Void`  
- `private ProcessMarkerNodes(Unity.Entities.DynamicBuffer<Game.Net.SubNet> subNets, System.Int32& lowVoltageCapacity, System.Int32& highVoltageCapacity, System.Int32& flow) : System.Void`  

