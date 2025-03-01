# qe2poscar
convert prefix.xml output by QE to POSCAR

Converting pw.in to POSCAR is difficult, but converting prefix.xml to POSCAR is much easier. Here's the process:
1. Run `mpirun -np $SLURM_NTASKS pw.x < pw.in > pw.out`
2. Use MATLAB code `readprefixxml(prefix)` to process `prefix.xml`, which will generate a POSCAR file named `prefix.vasp`

Alternatively, you can copy `qe2poscar.sh` to your Quantum ESPRESSO directory containing `prefix.xml`, and it will generate `prefix.vasp`.
1. Run `chmod +x qe2poscar.sh` to make the script executable
2. Execute the script by running `./qe2poscar.sh`

If you set `calculation='relax'` or `calculation='vc-relax'` in your pw.in file, the script will generate a POSCAR file with the relaxed atomic positions.
