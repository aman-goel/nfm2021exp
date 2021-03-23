#### Artifact for the NFM'21 paper - 
   
###   *On Symmetry and Quantification: A New Approach to Verify Distributed Protocols*
--------------------------------------------------------------------------
includes:
- all experimental data and logs
- all detailed results tables
- all evaluation scripts
- IC3PO source code for replicating the runs
- source code for each tool (all openly available) for replicating the runs

#### Resource requirements:
- 4 to 6 cores
- 8-16 GB RAM should be enough
- roughly 1-2 days for complete evaluation (on a ~3GHz Intel CPU)

#### Description
The artifact evaluates the tool IC3PO presented in the paper,
and compares it against other state-of-the-art verifiers fol-ic3, I4, UPDR.

The artifact consists of a total of 3 experiments that can be executed one 
by one to evaluate the paper contents.

Check the License.txt in the artifact for license information.

Note-
   If the experiments are too resource intensive for your machine,
   change the line timeMax="1000" to  timeMax="100" in the following files:
   - exp/ic3po/ic3po.sh
   - exp/i4/i4.sh
   - exp/mypyv/updr.sh
   - exp/mypyv/folic3.sh
   
   All compiled results are available in exp/results/* folder.
   All detailed logs are available in exp/<tool>/output*/* folder.
   
   Please contact the authors through the conference chairs for any
   technical help or clarification relating to reproducing the results
   or analyzing the experimental logs and scripts.
   
#### How to run
Make sure the artifact is in the /home/username/ directory.
This means, this file should be present at /home/username/artifact/README.txt

Installation:
```
  cd packages
  chmod +x install.sh
  sudo ./install.sh		# you may have to edit this file or install any missing package
  # the script may produce some warnings/python errors

  -- Add the following to your /home/username/.bashrc
  export EXPATH=/home/username/artifact/exp
  export IC3POPATH=$EXPATH/ic3po/ic3po
  export PYSMT_PATH=$IC3POPATH/pysmt
  export PYTHONPATH=$PYSMT_PATH:$PYTHONPATH
  
  source /home/username/.bashrc
  echo $EXPATH	# Make sure this returns /home/username/artifact/exp
  cd ..
  pwd			# Make sure this returns /home/username/artifact
```

There are total 3 scripts (named exp1.sh ... exp3.sh), that interactively goes through each experiment.
The scripts goes through each experiment interactively, and prints further details
on what part of the paper is the experiment trying to evaluate.
Simply run each script one by one, (have some coffee!) and press ENTER, and the scripts will guide you at each step.

Note- Experiment exp3.sh is completely optional. 
      They only evaluates the data in the appendix (included for additional completeness).
      Some experiments open a new terminal for each tool separately, to allow parallel runs
      Ignore linux warnings, if any.

For complete assessment, run:
```
  KICK=0 ./exp1.sh
  KICK=0 ./exp2.sh
  KICK=0 ./exp3.sh
```
  
All compiled results are produced in exp/results/* folder.
All detailed logs are produced in exp/<tool>/output*/* folder.

Once exp2 runs have completed, the results can be compiled into a table with:
```
  ./compile_main.sh         # check the table in exp/results/compiled/table.csv
```


##### IMPORTANT NOTE ON AVAILABILITY
The IC3PO tool is maintained on a public github repository-- 
	https://github.com/aman-goel/ic3po.

We would be glad to hear from you and help you in the case you are having a difficulty in using IC3PO
Please report bugs and share your usage experience via email  [(amangoel@umich.edu)](amangoel@umich.edu) or on github [(https://github.com/aman-goel/ic3po)](https://github.com/aman-goel/ic3po).
