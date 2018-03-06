# IBM Security Performance

## Identity and Access Management

### Useful tools

#### pstack analysis tools

This directory contains scripts for analyzing pstacks from current versions of Linux's pstack command in the gdb package.
Other versions may require slight changes to pstacksum.awk.

process_pstacks.sh will look for all files named *pstack* in the specified directory and process them with get_threadstacks_from_pstack.sh

get_threadstacks_from_pstack.sh will process the specified javacore using the pstacksum.awk script

pstacksum.awk takes the thread stacks in the specified file and flattens them with each thread on its own line.

For each XXpstackYY file in the directory, a corresponding file named XXthreadstacksYY with all the flattened stacks from the pstack is produced, sorted to group common stacks together.

These files are most usefully viewed using a text editor with word wrap turned off.