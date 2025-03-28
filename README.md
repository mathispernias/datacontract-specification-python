# Data Contract Specification (Python)

The pip module `datacontract-specification` to read and write YAML files using the [Data Contract Specification](https://datacontract.com). The pip module was extracted from the [Data Contract CLI](https://github.com/datacontract/datacontract-cli), which is its primary user.

## Installation

```bash
pip install datacontract-specification
```

## Usage

```python
from datacontract_specification import DataContractSpecification

# Load a data contract specification from a file
data_contract = DataContractSpecification.from_file('path/to/your/data_contract.yaml')
print(data_contract.to_yaml())

# Load a data contract specification from a string
data_contract_str = """
dataContractSpecification: 1.1.0
id: urn:datacontract:checkout:orders-latest
info:
  title: Orders Latest
  version: 2.0.0
  description: |
    Successful customer orders in the webshop.
    All orders since 2020-01-01.
    Orders with their line items are in their current state (no history included).
  owner: Checkout Team
  status: active
  contact:
    name: John Doe (Data Product Owner)
    url: https://teams.microsoft.com/l/channel/example/checkout
"""
data_contract = DataContractSpecification.from_string(data_contract_str)
print(data_contract.to_yaml())
```
