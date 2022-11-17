# fastagetseq
awk script to extract one or more sequences from a fasta file, given their identifiers (i.e. the first word of the title line). 
No need for preformatting the fasta file.

Possible usages:  
1. fastagetseq -v I=single_fasta_id  input.fasta  >  output.fasta
2. fastagetseq -v i=file_with_ids    input.fasta  >  output.fasta

Additional options:
 -v f=1       full search (very slow); if any input id is present in any part of a fasta header, the sequence is output
 -v n=index   take the $index field of fasta header as id. Can be combined with -F
              example to catch the third |-separated field:   fastagetseq -F\"|\" -v n=3 -v i=id_file   input.fasta > output.fasta
              
Note: if some ids are repeated in the input file, or if some ids are not found in the input file, messages are printed to stderr
