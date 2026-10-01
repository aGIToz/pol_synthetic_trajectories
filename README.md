# GMU Campus Trajectory Dataset

This dataset contains synthetic agent trajectories generated with the POL
(Patterns-of-Life) simulation framework on the George Mason University (GMU) campus map. 
See  https://github.com/azufle/pol for the used code and for the GMU shape files. 

## Simulation Period

The dataset contains trajectories for 1,000 simulated agents.

Simulation time range:

- Start: `2019-07-01T00:00:00.000`
- End: `2020-09-28T09:00:00.000`
- Duration: approx. `455 days and 9 hours`

## Files

The trajectory data is split into ten CSV files for Git LFS upload:

- `trajs1.csv`
- `trajs2.csv`
- `trajs3.csv`
- `trajs4.csv`
- `trajs5.csv`
- `trajs6.csv`
- `trajs7.csv`
- `trajs8.csv`
- `trajs9.csv`
- `trajs10.csv`

Each file contains the same header and a sequential chunk of the full
trajectory table. Read the files in numeric order from `trajs1.csv` to
`trajs10.csv`.

## Columns

```csv
simulationTime,location,agentId
```

- `simulationTime`: simulation timestamp.
- `location`: agent position as a WKT point.
- `agentId`: integer identifier of the simulated agent.

## Formats

- Datetime format: `YYYY-MM-DDTHH:mm:ss.SSS`
- Location format: `POINT (x y)`
- `x` is easting and `y` is northing in the dataset CRS.

Example:

```csv
2020-09-28T09:00:00.000,POINT (2339183.193679435 426355.999893681),999
```

## Coordinate Reference System

The GMU trajectory coordinates use:

```text
EPSG:32046 - NAD27 / Virginia North
```

To convert positions to latitude/longitude, transform from `EPSG:32046` to
`EPSG:4326`.

## Notes

- This dataset is made availabe under the Open Database License (ODbL) 1.0
- The data is synthetic and produced by simulation, not by tracking real people.
- The ten CSV files preserve the original row order.
- Each split file has `13,114,892` data rows plus one header row.
- Total data rows across all ten files: `131,148,920`.
