# ABRicate database for K-typing of *E. coli*
ABRicate database to identify K1, K2 and K5 genes in *Escherichia coli* WGS data.

# Quickstart
This database can be used by cloning/downloading the `ecoli_k` directory and running ABRicate as follows:

```
abricate --datadir $DB_DIR --db ecoli_k $INPUT
```

Where `$DB_DIR` is the directory where the `ecoli_k` directory has been copied and `$INPUT` points to the fasta genome you would like to type.

# Contents
The K1 capsule locus is defined based on the VFDB entry on K1 http://www.mgc.ac.cn/cgi-bin/VFs/vfs.cgi?VFID=VF0239. The overview from Fig 1A of Arredondo-Alonso et al. (2023)[^1] was used as guidance for identifying the loci encoding K2 and K5.

| K-type | Region 1  | Region 2 | Region 3 |
| ------ | --------- | -------- | -------- |
| K1     | kpsFEDUCS | neuECABD | kpsTM    |
| K2     | kpsFEDUCS | kslEDBCA | kpsTM    |
| K5     | kpsFEDUCS | kfiDCBA  | kpsTM    |

# Caveats
There is some variation in gene sequences between K1, K2 and K5. This is most pronounced for kpsT, where a typical K1 kpsT shares only about 70% nucleotide identity with kpsT of K2 or K5. With default ABRicate settings, kpsT from other K-types than K1 will thus be missed using this database. 

This database is limited (only three K-types represented at the moment) and the usual limitations of ABRicate apply. This includes e.g. that this is not suited for FASTQ data or that this might not detect these genes in fragmented FASTA assemblies.


# Contributions
If you have reference gene sequences useful to type other K-types, please open a pull request or contact me.

[^1]: Arredondo-Alonso, S., Blundell-Hunter, G., Fu, Z. et al. Evolutionary and functional history of the Escherichia coli K1 capsule. Nat Commun 14, 3294 (2023). https://doi.org/10.1038/s41467-023-39052-w