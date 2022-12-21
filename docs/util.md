---
title : Utils
layout : default
nav_order: 16
---

# convert.go
This file contains utilities to parse data as required in other parts of the program.

Functions in the file
- **ParseUint** - converts a string to an unsigned integer. Very standard implementation. If it cannot be converted, then 0 along with non-nil error is returned.

{: .info}
>2 objects are returned (converted unsigned integer, error).

- **ParseString** - Converts an unsigned integer to string.

---

# prog_dept.go
This file contains utilities to check and compare the program departments.

**Function isDoubleMajor** to check if the given branch ID is a double major branch ID or not. (returns boolean) 

{: .info }
> array of all double major program department IDs
> 
>  28: AE	| 29: BSBE	| 30: CE	| 31: CHE	|
>  32: CSE	| 33: EE	| 34: MSE	| 35: ME	|
>  96: CHM	| 36: ECO	| 37: MTH	| 97: SDS	|
>  98: PHY	|
