
# Vicinity Set Cover Algorithm for solving reference genes in the human genome

This notebook provides a solution to the *vicinity set cover problem* using all protein-coding genes in the human genome. It identifies a minimal set of reference genes whose vicinities (defined by a given threshold) collectively cover the entire genome.
For simplicity and demonstration purposes, the algorithm has been set up to process each chromosome individually. (e.g., solve the vicinity set cover problem using only genes on chromosome 1.)

## 🔧 How It Works

The main function:
```python
main(threshold, chromosome)
```
- Loads protein-coding gene data from a `protein2_full.pkl` file.
- Filters genes by the specified chromosome.
- Uses the given threshold (in base pairs) to determine gene neighborhoods (vicinities).
- Solves the vicinity set cover problem to select the minimal set of reference genes that cover the genome.

## ▶️ Example Usage

To run the main function inside the notebook:

```python
if __name__ == '__main__':
    # Set threshold to 20,000 base pairs
    threshold = 20000

    # Analyze genes on chromosome 1
    chromosome = 'chr1'

    # Run the algorithm
    reference_genes, vicinities_of_reference_genes = main(threshold, chromosome)
```

This will output:
- `reference_genes`: List of selected reference genes.
- `vicinities_of_reference_genes`: List of gene sets around each selected reference gene.

## 📁 Requirements

- A file named `protein2_full.pkl` containing gene data in a dictionary format.
- Run the cell that imports the necessary libraries.
- Run the preceeding cells that define the required functions.

## 💡 Notes

- Adjust `threshold` and `chromosome` values to analyze different regions of the genome.
- Make sure all necessary imports (e.g., `pickle`, `numpy`) are included.
