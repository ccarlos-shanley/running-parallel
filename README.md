## running-parallel
## Examples of parallel (GNU) usage

### running same job with multiple files at the same

ls *.fasta | parallel --verbose "prokka {} --prefix {.}_out"

### running same job with multiple files, specifying the number of simultaneous jobs (--jobs)

ls *.faa | parallel --jobs 1 --verbose "exec_annotation --cpu 28 -f mapper -p ~/databases/profiles -k ~/databases/ko_list -o {.}.ko {}"
