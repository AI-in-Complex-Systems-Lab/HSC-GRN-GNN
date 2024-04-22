The directory strucutre of BEELINE-data is as follows:

├── config-files
│   ├── Curated
│   │   ├── GSD.yaml
│   │   ├── HSC.yaml
│   │   ├── mCAD.yaml
│   │   └── VSC.yaml
│   └── Synthetic
│       ├── dyn-BFC.yaml
│       ├── dyn-BF.yaml
│       ├── dyn-CY.yaml
│       ├── dyn-LI.yaml
│       ├── dyn-LL.yaml
│       └── dyn-TF.yaml
├── inputs
│   ├── Curated
│   │   ├── GSD
│   │   │   ├── GSD-2000-1
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── GSD-2000-1-50
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── GSD-2000-1-70
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── ...
│   │   ├── HSC
│   │   │   ├── ...
│   │   ├── mCAD
│   │   │   ├── ...
│   │   ├── VSC
│   │   │   ├── ...
│   ├── Synthetic
│   │   ├── dyn-BFC
│   │   │   ├── dyn-BFC-100-1
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── dyn-BFC-200-1
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── dyn-BFC-500-1
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── dyn-BFC-2000-1
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── dyn-BFC-5000-1
│   │   │   │   ├── ExpressionData.csv
│   │   │   │   ├── PseudoTime.csv
│   │   │   │   └── refNetwork.csv
│   │   │   ├── ...
│   │   ├── dyn-BF
│   │   │   ├── ...
│   │   ├── dyn-CY
│   │   │   ├── ...
│   │   ├── dyn-LI
│   │   │   ├── ...
│   │   ├── dyn-LL
│   │   │   ├── ...
│   │   └── dyn-TF
│   │
│   └── scRNA-Seq
│       ├── hESC
│       │   ├── ExpressionData.csv
│       │   ├── GeneOrdering.csv
│       │   └── PseudoTime.csv
│       ├── hHep
│       │   ├── ExpressionData.csv
│       │   ├── GeneOrdering.csv
│       │   └── PseudoTime.csv
│       ├── mDC
│       │   ├── ExpressionData.csv
│       │   ├── GeneOrdering.csv
│       │   └── PseudoTime.csv
│       ├── mESC
│       │   ├── ExpressionData.csv
│       │   ├── GeneOrdering.csv
│       │   └── PseudoTime.csv
│       ├── mHSC-E
│       │   ├── ExpressionData.csv
│       │   ├── GeneOrdering.csv
│       │   └── PseudoTime.csv
│       ├── mHSC-GM
│       │   ├── ExpressionData.csv
│       │   ├── GeneOrdering.csv
│       │   └── PseudoTime.csv
│       └── mHSC-L
│           ├── ExpressionData.csv
│           ├── GeneOrdering.csv
│           └── PseudoTime.csv
└── README.txt

444 directories, 1295 files

Folder description:

    inputs/Curated: Datasets from Curated Models. Each dataset contains the following information:
    1) ExpressionData.csv: A file containing GxC matrix of gene expression data with Genes in rows and cells in columns
    2) PseudoTime.csv: A file containing pseduotime values for each cell. If there are multiple columns, 
                       it implies there are cells belonging to multiple trajectories. Here the pesudotime is obtained by running Slingshot.
    3) refNetwork.csv: A file containing the reference network (for evaluation)

    For each curated model, there are 10 datasets each with 2000 cells, obtained from different , obtained from different
    BoolODE simulations. Futher there are 10 datasets each with q=50 and q=70 dropouts. The folder names under inputs/Curated/ contain
    the model name, followed by the number of cells in that dataset, followed by sample number, followed by the dropout rates. For example,
    the name GSD-2000-1-50 represents the dataset from GSD model, with 2000 cells, sample number of 1, with the dropout rate of q=50. 


    inputs/Synthetic: Datasets from Synthetic Networks. Each dataset contains the following information:
    1) ExpressionData.csv: A file containing GxC matrix of gene expression data with Genes in rows and cells in columns
    2) PseudoTime.csv: A file containing pseduotime values for each cell. If there are multiple columns, 
                       it implies there are cells belonging to multiple trajectories. Here the pesudotime is the simulation time.
    3) refNetwork.csv: A file containing the reference network (for evaluation)

    For each synthetic network, there are 10 datasets each with varying number of cells (100, 200, 500, 2000, 5000), obtained from different
    BoolODE simulations. The folder names under inputs/Synthetic/ contain the model name, followed by the number of cells, followed by the 
    sample number. For example, the name dyn-LI-100-8 represents the dataset from LI (Linear) model, with 100 cells, and the sample number is 8. 


    inputs/scRNA-Seq: Datasets from five experimental single-cell RNA-Seq datasets. Each dataset contains the following information:
    1) ExpressionData.csv: A file containing GxC matrix of gene expression data with Genes in rows and cells in columns
    2) PseudoTime.csv: A file containing pseduotime values for each cell. If there are multiple columns, 
                       it implies there are cells belonging to multiple trajectories. Here the pesudotime is the simulation time.
    3) GeneOrdering.csv: A file containing variance (and p-value of this variance) of gene expression along the pseudotime ordering computed using 'gam' R package.


    The datasets are obtained from the following sources:
        - hHESC (Human Embryonic Stem Cells): Chu, L. F. et al. Single-cell RNA-seq reveals novel regulators of human embryonic stem cell differentiation to definitive endoderm. Genome Biol. 17, 173 (2016). 
        - hHep (Human Mature Hepatocytes): Camp, J. G. et al. Multilineage communication regulates human liver bud development from pluripotency. Nature 546, 533–538 (2017). 
        - mDC (Mouse Dendritic Cells) : Shalek, A. K. et al. Single-cell RNA-seq reveals dynamic paracrine control of cellular variation. Nature 510, 363–369 (2014). 
        - mESC (Mouse Embryonic Stem Cells): Hayashi, T. et al. Single-cell full-length total RNA sequencing uncovers dynamics of recursive splicing and enhancer RNAs. Nat. Commun. 9, 619 (2018).     
        - mHSC-E, mHSC-GM, mHSC-L (Mouse Hematopoietic Stem Cells; Erythroid (E), Granulocyte-Monocyte (GM), Lymphoid (L)): Nestorowa, S. et al. A single-cell resolution map of mouse hematopoietic stem and progenitor cell differentiation. Blood 128, 20–31 (2016). 


    config-files:
    The config files and the parameter values used for datasets from Synthetic/ and Curated/, used for running BEELINE. 
