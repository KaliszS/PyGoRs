## Variables & Data


### Scalar data types

<img src="src/data/scalar.png" alt="Scalar data types" width=80% style="margin-top: -4%;">


### Compound data types

<img src="src/data/compound.png" alt="Compound data types" width=100% style="margin-top: -4%;">


### Enumarations

```py
# python -> enum is just a set of symbolic names 
# bound to unique values
from enum import Enum

class FleetOperation(Enum):
    PROTECT: 1
    EXPLORE: 2
```

```rs
// rust -> enum allows to store more complex structures
// and lets each variant to have different signatures
enum FleetOperation {
    Protect {tradenode_id: u8},
    Explore,
}

fn fleet_moves(operation: FleetOperation) {
    match operation {
        FleetOperation::Protect { tradenode_id } => //print sth
        // ...
    }
}
```


### Variables

<img src="src/data/variables.png" alt="Variables" width=85% style="margin-top: -4%;">


### Operators

<img src="src/data/operators.png" alt="Operators" width=120% style="margin-top: -4%; margin-left: -10%;">
