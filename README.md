# Randomly Generated Instances for the Multiple Periods, Multiple Depots, and Multiple Trips Vehicle Routing Problem with Time Windows (MMMVRPTW)

This repository contains randomly generated instances used for the sensitivity analysis in the paper:

**[Insert Paper Title Here]**  
*Authors: [Your Name(s)]*  
*Published in: [Conference/Journal Name]*  
*Year: [Year]*

## Overview

The instances are based on geographical areas in three Italian provinces:

- **Turin**
- **Milan**
- **Palermo**

For each province, three different scenarios are provided, varying by the number of depots and customers:

- **2 depots, 100 customers**
- **2 depots, 150 customers**
- **3 depots, 200 customers**

Each scenario is stored in an Excel file. The repository is structured as follows:

```
.
├── Turin/
│   ├── Turin_2d_100c.xlsx
│   ├── Turin_2d_150c.xlsx
│   └── Turin_3d_200c.xlsx
├── Milan/
│   ├── Milan_2d_100c.xlsx
│   ├── Milan_2d_150c.xlsx
│   └── Milan_3d_200c.xlsx
├── Palermo/
│   ├── Palermo_2d_100c.xlsx
│   ├── Palermo_2d_150c.xlsx
│   └── Palermo_3d_200c.xlsx
```

## Excel File Structure

Each Excel file contains two sheets:

### Sheet: `Depots`

| ID  | X       | Y       |
|-----|---------|---------|
| 1   | 9.2001  | 45.4653 |
| 2   | 9.1805  | 45.4707 |
| ... | ...     | ...     |

- **ID**: Unique identifier for each depot.
- **X**, **Y**: Coordinates of the depot in latitude/longitude or projected UTM system, depending on the instance set.

### Sheet: `Customers`

| ID  | X       | Y       | Demand |
|-----|---------|---------|--------|
| 1   | 9.1820  | 45.4642 | 10     |
| 2   | 9.1745  | 45.4601 | 7      |
| ... | ...     | ...     | ...    |

- **ID**: Unique identifier for each customer.
- **X**, **Y**: Coordinates of the customer.
- **Demand**: Demand associated with the customer (e.g., in units or weight). This is used in the optimization model.

Note: All coordinates are randomly generated within the administrative boundaries of the respective province.

## Purpose

These instances were created for **sensitivity analysis** in the referenced paper, specifically to explore how performance varies with geography, customer density, and number of depots.

