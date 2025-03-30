```plantuml
@startuml

' Abstract classes
abstract class Resource {
  -_name: str
  -_is_available: bool
  -_resource_type: ResourceType
  +name: str <<property>>
  +resource_type: ResourceType <<property>>
  +is_available_for_use(): bool <<abstract>>
  +allocate(): None <<abstract>>
  +release(): None <<abstract>>
  +use(): None <<abstract>>
}

enum ResourceType {
  CONSUMABLE
  USABLE
}

class ConsumableResource {
  -_total_capacity: int
  -_remaining_capacity: int
  +__init__(name: str, capacity: int)
  +is_available_for_use(): bool
  +allocate(): None
  +release(): None
  +use(): None
  +remaining_capacity: int <<property>>
}

class UsableResource {
  -_capacity: int
  +__init__(name: str, capacity: int)
  +is_available_for_use(): bool
  +allocate(): None
  +release(): None
  +use(): None
}

abstract class Executable {
  -_name: str
  -_description: str
  -_required_resources_names: List[str]
  -_duration_in_units: int
  -_assigned_resources: List[Resource]
  +__init__(name: str, description: str, required_resources_names: List[str], duration_in_units: int)
  +name: str <<property>>
  +required_resources_names: List[str] <<property>>
  +duration_in_units: int <<property>>
  +assign_resources(resource_pool: List[Resource]): None
  +release_resources(): None
  +execute(): None <<abstract>>
  +can_execute(resource_pool: List[Resource]): bool
}

class Task {
  +__init__(name: str, description: str, required_resources_names: List[str], duration_in_units: int)
  +execute(): None
}

class Process {
  -_resource_pool: List[Resource]
  -_tasks: List[Executable]
  +__init__(name: str, description: str, required_resources_names: List[str], duration_in_units: int)
  +add_resource(resource: Resource): None
  +add_task(task: Executable): None
  +execute(): None
  +run(): None
}

' Relationships
Resource o--> "1" ResourceType : uses
ConsumableResource -up-|> Resource : inherits
UsableResource -up-|> Resource : inherits
Executable o--> "many" Resource : uses
Task -up-|> Executable : inherits
Process -up-|> Executable : inherits
Process o--> "many" Resource : manages
Process o--> "many" Executable : manages

@enduml
```
