# qe2poscar
convert prefix.xml output by QE to POSCAR

Converting pw.in to POSCAR is difficult, but converting prefix.xml to POSCAR is much easier. Here's the process:
1. Run `mpirun -np $SLURM_NTASKS pw.x < pw.in > pw.out`
2. Use MATLAB code `readprefixxml(prefix)` to process prefix.xml, which will generate a POSCAR file named 'prefix.vasp'.
