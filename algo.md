## Quick start

### Requirements
* Linux or macOS

### Install ANNOVAR

Follow the instructions to download ANNOVAR at:
> [http://www.openbioinformatics.org/annovar/annovar_download_form.php](http://www.openbioinformatics.org/annovar/annovar_download_form.php)

Once downloaded, unpack the package by using this command:

```
tar -zxvf annovar.latest.tar.gz
```

### Download HADA

In ANNOVAR folder, download HADA database and index files from repository:

```
cd annovar
wget https://raw.githubusercontent.com/genomicsITER-developers/HADA/master/releases/latest/hg19_hada_20190131.txt -P humandb
wget https://raw.githubusercontent.com/genomicsITER-developers/HADA/master/releases/latest/hg19_hada_20190131.txt.idx -P humandb
```

### Annotate a VCF

Annotate a VCF file using HADA:
```
perl <path-to-annovar-dir>/table_annovar.pl <path-to-vcf-infile> <path-to-annovar-dir>/humandb \
  -buildver hg19 \
  -out <path-to-vcf-outfile> \
  -remove \
  -protocol hada_20190131 \
  -operation f \
  -nastring . \
  -vcfinput
```

**Note:** remember to replace the items in "<>"" with your local paths in your computer:

&lt;path-to-annovar-dir> : path (directory) where ANNOVAR is installed

&lt;path-to-vcf-infile> : path (file) where input VCF is stored

&lt;path-to-vcf-outfile> : path (file) where the resulting annotated VCF will be stored
