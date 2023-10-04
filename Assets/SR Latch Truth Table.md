# Without Enabler

| S   | R   | Q   | Q'  | Condition      |
| --- | --- | --- | --- | -------------- |
| 0   | 0   | Q   | Q'  | Previous state |
| 1   | 0   | 1   | 0   | SET            |
| 0   | 1   | 0   | 1   | RESET          |
| 1   | 1   | X   | X   | Forbidden      |

# With Enabler

| EN  | S   | R   | Q   | Q'  | Condition |
| --- | --- | --- | --- | --- | --------- |
| 0   | X   | X   | Q   | Q'  | No Change |
| 1   | 0   | 0   | Q   | Q'  | No Change | 
| 1   | 1   | 0   | 1   | 0   | SET       |
| 1   | 0   | 1   | 0   | 1   | RESET     |
| 1   | 1   | 1   | X   | X   | Forbidden |