# AKI gut microbiota metabolite analysis

Version prepared for the first revision of *Gut microbiota-associated metabolites and inflammatory signaling in acute kidney injury: network pharmacology and cellular evaluation of butyrate*.

## Code map

| Directory | Analysis |
|---|---|
| Computational/2–6 | SEA/STP target aggregation, AKI and host-gene intersections, and Figure 2 |
| Computational/7–9 | STRING network centrality, enrichment and the GeneMANIA expansion for Figures 3–5 |
| Computational/10–14 | Expanded enrichment, pathway mapping, MCODE and the integrated network for Figures 6–10 |
| Computational/15 | Exploratory docking and Figure 11 |
| Revision_recheck | Archived cellular statistics audit for Supplementary Table S9 |
| Revision_checks | CID matching, disease filters, network and enrichment sensitivity for Supplementary Table S10 |

The numbered directories retain the archived source layout and script names. The corresponding manuscript supplements are Supplementary Data S1 (computational), S2 (cellular) and S3 (revision checks). Inputs must be placed in their original subdirectories relative to the scripts. Some historical scripts need local software paths configured, particularly R library paths, Cytoscape automation, fonts and the Vina executable. The source manifest records provenance and checksums. Machine-specific home/workspace paths were replaced in the release copy. The statistical and bioinformatics algorithms were preserved. This archive is a code snapshot; an end-to-end rebuild from a fresh checkout has not been validated.

Run the revision sensitivity entry point with Python and openpyxl as follows, pointing to the archived computational input tree. Use a separate output directory.

```sh
python Revision_checks/recheck.py --input-root PATH_TO_ARCHIVED_INPUTS --output-dir PATH_TO_OUTPUT
```

The cellular audit uses NumPy and SciPy and reads its archived files from `Revision_recheck/qa/`. The main network stages use NumPy, NetworkX and venn, with R/Bioconductor packages clusterProfiler, org.Hs.eg.db, GO.db, AnnotationDbi and pathview where specified. The docking workflow uses the versions documented in the manuscript and its supplementary tables.

Third-party software copies, external database exports, original cell measurements and membrane image files are supplied or documented separately in the manuscript supplements, subject to their applicable terms. This code snapshot does not reproduce those archives.
