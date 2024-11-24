# AHP Weight Calculation for Land Suitability Variables

## 1. Define Key Variables
Common variables for land suitability analysis:
1. Slope
2. Soil Type
3. Land Use/Land Cover
4. Distance to Water Sources
5. Distance to Roads
6. Elevation

## 2. Pairwise Comparison Matrix
Scale of relative importance:
- 1: Equal importance
- 3: Moderate importance
- 5: Strong importance
- 7: Very strong importance
- 9: Extreme importance
- 2,4,6,8: Intermediate values

Pairwise Comparison Matrix:
|  Variables  | Slope | Soil | LULC | Water | Roads | Elevation |
|------------|-------|------|------|-------|-------|-----------|
| Slope      | 1     | 2    | 3    | 4     | 5     | 6        |
| Soil       | 1/2   | 1    | 2    | 3     | 4     | 5        |
| LULC       | 1/3   | 1/2  | 1    | 2     | 3     | 4        |
| Water      | 1/4   | 1/3  | 1/2  | 1     | 2     | 3        |
| Roads      | 1/5   | 1/4  | 1/3  | 1/2   | 1     | 2        |
| Elevation  | 1/6   | 1/5  | 1/4  | 1/3   | 1/2   | 1        |

## 3. Normalized Matrix and Weight Calculation

Decimal Form Matrix:
|  Variables  | Slope  | Soil   | LULC   | Water  | Roads  | Elevation |
|------------|--------|--------|--------|--------|--------|-----------|
| Slope      | 1.000  | 2.000  | 3.000  | 4.000  | 5.000  | 6.000    |
| Soil       | 0.500  | 1.000  | 2.000  | 3.000  | 4.000  | 5.000    |
| LULC       | 0.333  | 0.500  | 1.000  | 2.000  | 3.000  | 4.000    |
| Water      | 0.250  | 0.333  | 0.500  | 1.000  | 2.000  | 3.000    |
| Roads      | 0.200  | 0.250  | 0.333  | 0.500  | 1.000  | 2.000    |
| Elevation  | 0.167  | 0.200  | 0.250  | 0.333  | 0.500  | 1.000    |
| Sum        | 2.450  | 4.283  | 7.083  | 10.833 | 15.500 | 21.000   |

Normalized Matrix and Final Weights:
|  Variables  | Slope  | Soil   | LULC   | Water  | Roads  | Elevation | Weights |
|------------|--------|--------|--------|--------|--------|-----------|----------|
| Slope      | 0.408  | 0.467  | 0.424  | 0.369  | 0.323  | 0.286    | 37.9%    |
| Soil       | 0.204  | 0.233  | 0.282  | 0.277  | 0.258  | 0.238    | 24.9%    |
| LULC       | 0.136  | 0.117  | 0.141  | 0.185  | 0.194  | 0.190    | 16.0%    |
| Water      | 0.102  | 0.078  | 0.071  | 0.092  | 0.129  | 0.143    | 10.2%    |
| Roads      | 0.082  | 0.058  | 0.047  | 0.046  | 0.065  | 0.095    | 6.5%     |
| Elevation  | 0.068  | 0.047  | 0.035  | 0.031  | 0.032  | 0.048    | 4.4%     |

## 4. Final Weight Percentages
1. Slope: 37.9%
2. Soil Type: 24.9%
3. Land Use/Land Cover: 16.0%
4. Distance to Water: 10.2%
5. Distance to Roads: 6.5%
6. Elevation: 4.4%

## 5. Consistency Ratio (CR) Check
λmax = 6.122
CI (Consistency Index) = (λmax - n)/(n-1) = 0.024
RI (Random Index for n=6) = 1.24
CR = CI/RI = 0.019 (< 0.10, therefore acceptable)

## 6. Weight Overlay Formula
Land Suitability = (0.379 × Slope) + (0.249 × Soil) + (0.160 × LULC) + 
                   (0.102 × Water) + (0.065 × Roads) + (0.044 × Elevation)

Note: Each variable should be standardized to a common scale (e.g., 1-5 or 1-10) before applying the weights.
