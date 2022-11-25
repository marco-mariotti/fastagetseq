# fastagetseq
awk script to extract one or more sequences from a fasta file, given their identifiers (i.e. the first word of the title line). 
No need for preformatting the fasta file.

Two possible usages:  
```
fastagetseq -v I=single_fasta_id  input.fasta  >  output.fasta
fastagetseq -v i=file_with_ids    input.fasta  >  output.fasta
```

Additional options:

```
-v f=1       full search (very slow); search for input ids in the whole fasta header (not just the first word)
-v n=index   take the $index field of fasta header as id. Can be combined with -F
```
 
Example to catch the third |-separated field:   

```
fastagetseq -F\"|\" -v n=3 -v i=id_file   input.fasta > output.fasta
```

Note: if some ids are repeated in the input file, or if some ids are not found in the input file, messages are printed to stderr
