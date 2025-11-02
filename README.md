# Leslie Matrix App

A comprehensive web-based calculator for Leslie matrix analysis, designed for population dynamics modeling and eigenvalue computation. This tool provides an intuitive interface for demographers, ecologists, and researchers working with age-structured population models.

**Live Website:** https://evcal.ndulina.com/

## Overview

### Purpose
The Leslie Matrix App is a specialized calculator designed to analyze age-structured population dynamics using Leslie matrices. It enables users to model population growth, calculate eigenvalues and eigenvectors, and understand long-term population behavior through mathematical analysis.

### About Leslie Matrices
Leslie matrices are square matrices used in population ecology to model the growth of age-structured populations. Named after P.H. Leslie who introduced them in 1945, these matrices incorporate:
- **Survival rates**: The probability that individuals in one age class survive to the next
- **Fecundity rates**: The average number of offspring produced by individuals in each age class

The matrix structure allows researchers to project population distributions over time and analyze long-term growth rates through eigenvalue decomposition.

### Eigenvalue Theory
The dominant eigenvalue (largest in absolute value) of a Leslie matrix represents the asymptotic population growth rate:
- **λ > 1**: Population grows exponentially
- **λ = 1**: Population remains stable
- **λ < 1**: Population declines toward extinction

The corresponding eigenvector represents the stable age distribution that the population will eventually approach.

## Features

### Matrix Input Options
- **21x21 Grid Input**: Interactive grid interface for manual entry of matrix values with real-time validation
- **CSV File Upload**: Import complete Leslie matrices from CSV files for quick analysis
  - Supports full matrix upload with automatic parsing
  - Validates matrix dimensions and data format

### Computational Capabilities
- **Power Iteration Algorithm**: Robust eigenvalue computation using the power iteration method
  - Calculates the dominant eigenvalue (growth rate)
  - Determines the corresponding eigenvector (stable age distribution)
  - Iterative convergence for accurate results

### Results Display
- **Results Positioned Above Matrix**: Clear presentation of computational results displayed prominently above the input matrix
  - Dominant eigenvalue (λ)
  - Eigenvector components
  - Interpretation of population growth dynamics

### User Interface
- **Minimalist Design**: Clean, distraction-free interface focused on functionality
- **Professional Styling**: Modern, professional appearance suitable for academic and research use
- **Responsive Layout**: Works seamlessly across desktop and mobile devices
- **Intuitive Navigation**: Easy-to-use controls with clear labeling and helpful tooltips

## Usage Instructions

### Matrix Entry Methods

#### Manual Grid Input
1. Navigate to the input grid on the main page
2. Click on each cell to enter values
3. Enter survival rates in the subdiagonal (probability of surviving to next age class)
4. Enter fecundity rates in the first row (reproductive output by age class)
5. Leave other cells as zero (standard Leslie matrix structure)
6. Click "Calculate" to compute eigenvalues

#### CSV File Upload
1. Prepare your Leslie matrix in CSV format (see format specifications below)
2. Click the "Upload CSV" button
3. Select your CSV file from your computer
4. The matrix will be automatically populated in the grid
5. Review the imported values for accuracy
6. Click "Calculate" to perform analysis

### CSV Format Specifications
Your CSV file should contain a 21x21 matrix with the following structure:
```
f1,f2,f3,...,f21
s1,0,0,...,0
0,s2,0,...,0
...
0,0,0,...,s20
```

Where:
- `f1, f2, ..., f21` are fecundity rates (first row)
- `s1, s2, ..., s20` are survival rates (subdiagonal)
- All other entries should be 0

**Example CSV format:**
```csv
0.5,1.2,1.8,2.0,1.5,0.8,0.3,0,0,0,0,0,0,0,0,0,0,0,0,0,0
0.7,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
0,0.8,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
0,0,0.85,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0
```
(Continue for all 21 rows)

### Output Interpretation

The calculator provides the following results:

1. **Dominant Eigenvalue (λ)**: 
   - Represents the long-term population growth rate
   - Value > 1: Population increases exponentially
   - Value = 1: Population stable (replacement level)
   - Value < 1: Population declining

2. **Eigenvector**: 
   - Shows the stable age distribution
   - Each component represents the proportion of the population in that age class at equilibrium
   - Useful for understanding long-term population structure

3. **Convergence Information**:
   - Number of iterations required
   - Convergence tolerance achieved

## Technical Details

### Algorithm
The application uses the **Power Iteration Method** for eigenvalue computation:
1. Starts with an initial vector
2. Repeatedly multiplies by the Leslie matrix
3. Normalizes the result after each iteration
4. Continues until convergence (successive iterations produce similar results)
5. Returns the dominant eigenvalue and corresponding eigenvector

### Performance
- Fast computation for standard 21x21 matrices
- Convergence typically achieved within 50-100 iterations
- Client-side processing (no server required)

## Deployment

### Live Application
The Leslie Matrix App is deployed and accessible at:
**https://evcal.ndulina.com/**

### Local Development
To run the application locally:
1. Clone this repository
2. Open `index.html` in a modern web browser
3. No build process or dependencies required - pure HTML/CSS/JavaScript

### Browser Compatibility
- Chrome (recommended)
- Firefox
- Safari
- Edge
- Any modern browser with JavaScript enabled

## Use Cases

- **Population Ecology**: Model wildlife populations with age-structured dynamics
- **Conservation Biology**: Assess population viability and extinction risk
- **Demography**: Analyze human population growth and age structure
- **Education**: Teaching tool for population dynamics and linear algebra
- **Research**: Quick calculations for academic papers and reports

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests to improve the application.

## License

This project is open source and available for educational and research purposes.

## Contact

For questions, suggestions, or bug reports, please open an issue on this repository.

---

**Visit the live application:** https://evcal.ndulina.com/
