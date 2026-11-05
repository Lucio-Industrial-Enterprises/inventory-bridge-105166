# Warehouse tools

Small Python utilities for warehouse order and shipping workflows.

Run the tests with `python3 -m unittest discover -s tests -v`.

## Shipping

`shipping_quote(weight_kg, zone, service="standard")` returns a delivery quote
in dollars. Zones are `local` and `regional`; weights must be positive.
Service levels are `standard` (default) and `express` (adds $7 to the base
rate). Unknown zones or services raise `ValueError`.

The command-line entry point prints a quote for an order:

```
python -m warehouse.cli 5 regional
python -m warehouse.cli 5 regional --service express
```
