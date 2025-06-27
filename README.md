# Randomly Generated Instances for the Multiple Periods, Multiple Depots, and Multiple Trips Vehicle Routing Problem with Time Windows (MMMVRPTW)

This repository contains randomly generated instances used for the computational experiments in the paper:

**Solving a Rich Vehicle Routing Problem with Time Windows in Pharmaceutical Distribution**  
*Authors: Mirko Cavecchia, Thiago Alves de Queiroz, Riccardo Lancellotti, Giorgio Zucchi, Manuel Iori*  
*Year: [2025]*

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
├── Milan/
│   ├── Milan_2d_100c.xlsx
│   ├── Milan_2d_150c.xlsx
│   └── Milan_3d_200c.xlsx
├── Palermo/
│   ├── Palermo_2d_100c.xlsx
│   ├── Palermo_2d_150c.xlsx
│   └── Palermo_3d_200c.xlsx
├── Turin/
│   ├── Turin_2d_100c.xlsx
│   ├── Turin_2d_150c.xlsx
│   └── Turin_3d_200c.xlsx
```

## Excel File Structure

Each Excel file contains **three sheets**, described below:

### 1. Sheet: `Customer Info`

This sheet includes detailed information on both depots and customers.

| ID | Type | Province | Latitude | Longitude | TW-a | TW-b | mo_dem | ... | sa_dem | mo_serv | ... | sa_serv | largest vehicle id |
|----|------|----------|----------|-----------|------|------|--------|-----|--------|----------|-----|----------|---------------------|
| 0  | M    | Palermo  | 37.7704  | 13.3419   | 360  | 1440 | 0      | ... | 0      | 0        | ... | 0        | 0                   |

- **ID**: Progressive index starting from 0.
- **Type**: Indicates the node type:
  - `M`: Main depot (only one per instance).
  - `P`: Additional depots (if any).
  - `HP`: Large customer.
  - `H`: Medium-sized customer.
  - `T`: Small customer.
- **Province**: The province to which the node belongs.
- **Latitude**, **Longitude**: Geographical coordinates randomly generated through [QGIS](https://qgis.org/).
- **TW-a**, **TW-b**: Start and end of the allowed time window (in minutes from midnight).
- **mo_dem – sa_dem**: Daily demand from Monday to Saturday.
- **mo_serv – sa_serv**: Service time required each day.
- **Largest vehicle id**: Maximum vehicle type allowed to serve this node.

> **Note:** Customer types follow a fixed ratio in all instances:
> - 10% are `HP`
> - 20% are `H`
> - 70% are `T`

### 2. Sheet: `Distance Matrix`

This sheet contains the full distance matrix (in kilometers) between all nodes (depots + customers).

- Matrix dimensions: *(#depots + #customers) x (#depots + #customers)*  
- Distances have been computed using the [Open Source Routing Machine (OSRM)](https://project-osrm.org/).

### 3. Sheet: `Vehicle Description`

This sheet provides the characteristics of the vehicle types available in each depot.

| ID | Capacity | Cost |
|----|----------|------|
| 0  | 60       | 160  |
| 1  | 45       | 140  |
|... | ...      | ...  |

- **ID**: Vehicle type identifier.
- **Capacity**: Maximum load capacity.
- **Cost**: Associated cost per vehicle usage.

## Purpose

These instances were created to test the proposed methods to address a rich vehicle routing problem with time windows, specifically to explore how performance varies with customer density and number of depots. The instances are designed to support research on complex vehicle routing problems involving:

- Multiple periods (daily demand and service over a 6-day week)
- Multiple depots
- Multiple trips per vehicle
- Time windows
- Heterogeneous vehicle fleets with access restrictions