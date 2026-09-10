# AquaScan Water Analysis

AquaScan is a shell-based simulation that generates sample water-quality readings and writes a timestamped text report.

## Important limitation

The current script uses Bash's pseudo-random number generator. It does **not** read a physical sensor, laboratory result, public dataset, or calibrated instrument. Its “safe” or “unsafe” output is demonstration logic and must not be used to decide whether water is safe to drink.

## What the script generates

- pH
- turbidity in NTU
- temperature in degrees Celsius
- hardness in mg/L
- mineral-content estimate in ppm
- a random quality score

The current safety rule flags pH outside 6.5–8.5 or turbidity above 5 NTU. These thresholds are implemented for demonstration only and do not constitute a complete safety assessment.

## Requirements

- Bash
- `bc`

## Run

```bash
chmod +x analysis.sh
./analysis.sh
```

The script creates `analysis_report_<timestamp>.txt` in the current directory. Generated reports are ignored by Git.

## Future work

- Accept explicit measurements as command-line or file input.
- Validate units, ranges, missing values, and malformed data.
- Cite the standards used for every threshold.
- Add fixture-based tests and ShellCheck.
- Separate simulation mode from real-data analysis.
