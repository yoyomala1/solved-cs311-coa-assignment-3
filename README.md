Download Link: https://assignmentchef.com/product/solved-cs311-coa-assignment-3
<br>
<span class="kksr-muted">Rate this product</span>

Develop a single cycle processor simulator for ToyRISC. Input to the Program

<ol>

 <li>full path to the configuration file. A sample file is given at src/configuration/config.xml. This describes the processor to be simulated. This is not of much use inthis assignment, but will be utilized in coming assignments.</li>

 <li>full path to the statistics file to be created. This file contains the statistics of the simulation run – number of instructions executed, number of cycles taken, etc.</li>

 <li>full path to the object file whose execution is to be simulated.</li>

</ol>

Output of the Program

• the program must create the statistics file at the specified location. Broad Outline of the Steps

<ul>

 <li>The source is available at gitea. git clone https://gitea.iitdh.ac. in:443/rajshekar.k/CS311_assignment3.git</li>

 <li>Loading of the program: Begin with implementing the loadProgram function in the file Simulator.java. Store the global data and instruc- tions in the approporiate locations in the mainMemory structure (see Sec- tion “Address Space Layout” in assignment 1). Set the PC register to the memory address of the first instruction (remember from assignment 2 that this is the first integer in the object file). Set x0= 0, x1= 216 − 1, and x2= 216 − 1.You can check the contents of the memory using processor.getMainMemory() .getContentsAsString(&lt;starting-address&gt;, &lt;ending-address&gt;).</li>

 <li>Simulation of the program:– The function simulate() in the file src/generic/Simulator.java describes the overall loop that captures the simulation. The five stages of the processor are called in-order.1</li>

</ul>

<ul>

 <li>–  As discussed in class, between every two stages, there is a latch. Thecontents of the different latches are obviously different. Therefore, foreach latch type, a separate class has been created. For example, theIF-OF latch is described by the file src/processor/pipeline/IF OF LatchType.java. An object of this type is created, and references to the same objectare given to both the IF stage and the OF stage.You have to decide the contents of each latch. IF OF LatchType has been done for you. Similarly, implement the remaining latches.</li>

 <li>–  Implement each of the stages. The IF stage has been implemented for you. Similarly, implement the remaining stages.</li>

 <li>–  The simulation ends when an end instruction passes through the IFstage. Call setSimulationComplete() (defined in the file src/generic/Simulator.java) at this point.</li>

 <li>–  Set the statistics – number of instructions executed and the numberof cycles taken – once the simulation is completed. You may do thisat the end of the simulate() function. To do the setting, call the appropriate functions in the file src/generic/Statistics.java.You are encouraged to add statistics of your own in the file Statistics.java.• Tabulate cycles and instruction counts for all programs that you submitted as part of assignment 1, in your report. These programs will function as benchmarks for the our processor designs.TestingFive example ToyRISC programs, their object codes, and the corresponding ex- pected system state at the end of execution, are given in the supporting files archive. Also, the simulator prints a hash value – a hash of the processor state – at the end of the execution. The expected correct hash values are also given.Run python test zip.py &lt;path to zip file&gt; to check your submission.Follow the same naming convention: “&lt;roll-number-1&gt; &lt;roll-number-2&gt; assignment3.zip”.Note• All subsequent assignments in this course will involve modifying this set of source files. You will be adding many more files to this project. Please use version controlling extensively, and back up your code frequently.• You will have two weeks to submit this assignment.</li>

</ul>