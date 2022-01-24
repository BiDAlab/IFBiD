# 

# IFBiD Databases
IFBiD: Inference-Free Bias Detection

## DOWNLOAD DigitWdb and GenderWdb Databases

+ Download [DigitWdb](http://atvs.ii.uam.es/atvs/intranet/free_DB/beCAPTCHA).

+ Download [GenderWdb](http://atvs.ii.uam.es/atvs/intranet/free_DB/beCAPTCHA).
 
+ For more information, please contact: **atvs@uam.es**


## DESCRIPTION OF DigitWdb and GenderWdb
We have created two databases for experimenting in automatic bias detection: DigitWdb and GenderWdb. The databases contain the weights Ω of the models φ(·,|Ω) used
in our experiments for the tasks of digit and gender classification: 

### DigitWdb: 48K digit classification networks
The architecture is the same for all models: a CNN φ(·|Ω) with three convolutional layers with relu activation, each followed by a maxpool, and two fully connected layers at the end (with 128 and 10 neurons, a relu and a softmax activation function respectively), with a dropout layer of 0.3 between the two. Each of the trained models results in a total of 50K parameters.

**• Train:** 40K models classified by bias level into four groups, with 10K models per level. The models were trained using the first 30K training digits from [Colored MNIST](https://github.com/feidfoe/learning-not-to-learn). The models have been categorized into four groups depending on the replica subset with which they have been trained. The level of bias of the replica subset is what determines the level of bias of the model. Groups are: very high bias (color jitter variance of 0.02), high bias (color jitter variance of 0.03), low bias (color jitter variance of 0.04), and very low bias (color jitter variance of 0.05).

**• Test:** 8K models classified by bias level into four groups (2K models for each level). The models were trained using the last 30K training digits from [Colored MNIST](https://github.com/feidfoe/learning-not-to-learn) and categorized in the same way as the training ones (i.e., from very high bias to very low bias).

The digits for Train and for Test belong to independent sets.

**Average digit classification accuracy in DigitWdb models according to their level of bias. The more bias, the worse the classification accuracy of each digit.**
<table>
  <tr align="center">
    <th>Model<br>Bias</th>
    <th colspan="10">Digit Classification Accuracy (%)</th>
  </tr>
   <tr align="center">
    <th></th><th>0<th>1<th>2<th>3<th>4<th>5<th>6<th>7<th>8<th>9
  </tr>
  <tr align="center"><td align="left">Very Low	 <td>	88  <td> 94 <td> 77 <td> 82 <td> 90 <td> 89 <td> 75 <td> 84 <td> 81 <td> 82 </tr>
  <tr align="center"><td align="left">Low	      <td>	79  <td>  85  <td>  67  <td>  69  <td>  81  <td>  83  <td>  65  <td>  76  <td>  72  <td>  69 </tr>
  <tr align="center"><td align="left">High	     <td>	66  <td>  76  <td>  54  <td>  56  <td>  72  <td>  69  <td>  49  <td>  64  <td>  58  <td>  46	</tr>
  <tr align="center"><td align="left">Very High	<td>	49  <td>  51  <td>  42  <td>  38  <td>  59  <td>  40  <td>  40  <td>  51  <td>  43  <td>  32 </tr>
</table>


### GenderWdb: 36K gender classification networks
The architecture is the same for all models: a CNN with six convolutional layers with relu activation, each followed by a maxpool, and two fully connected layers at the end (with 128 and two neurons, a relu and a softmax activation function respectively). The result is a model with a total of 100K parameters.

**• Train:** 30K models belonging to three classes of bias, with 10K models per class. Models were trained with the [DiveFace](https://github.com/BiDAlab/DiveFace) database of face images. Bias was introduced by unbalancing each ethnic group during training: asian, African/Indian, and Caucasian.

**• Test:** 6K models belonging to three classes of bias. Models were trained using face images from [DiveFace], and bias was introduced by unbalancing each ethnic group

The face images for Train and for Test belong to independent sets.

**Properties**

<!-- ![](https://github.com/BiDAlab/BeCAPTCHA-Mouse/blob/master/Fig5.png) -->


#### BENCHMARK STRUCTURE
BeCAPTCHA-Mouse benchmark are composed by two main folders: *'DB_GAN'* which contains the synthetic GAN trayectories and *'DB_fnc'* that contains the function-based ones. Each main folder has other two folders: *'raw'* folder which contains the raw data of the synthetic mouse trayectories in .txt files, and *'neuromotor'* folder that contains the Sigma-Lognormal descomposition (more details in [3]) of the raw files in .ana format. Both kind of files have the same name to match them easily.

#### FILES FORMAT
+ .txt files: it just contains two columns with the **{x̂, ŷ}** mouse coordinates.
  + COLUMN 1: represents the **x̂** coordinate.

  + COLUMN 2: represents the **ŷ** coordinate.

+ .ana files: each row contains a log-normal signal extracted from the synthetic mouse trayectory, this log-normal signal is definded by 6 parameters. One parameter in each column:  

  + COLUMN 1: represents the *D* parameter.

  + COLUMN 2: represents the *t<sub>0</sub>* parameter.

  + COLUMN 3: represents the *μ* parameter.

  + COLUMN 4: represents the *σ* parameter.

  + COLUMNS 5 : represents the *θ<sub>s</sub>* parameter.
  
  + COLUMNS 6 : represents the *θ<sub>e</sub>* parameter.
  
  + COLUMNS 7, 8: are zeros.
  

#### FILES NOMENCLATURE
The nomenclature followed to name the files of the function-based method is: NNNN_y=A_vp=B_task=C.txt

+ NNNN: indicates the number of the sample.

+ A: indicates the shape of the trajectory:

  + 0 = linear.
  
  + 1 = quadratic.
  
  + 2 = exponential.
  
+ B: indicates the velocity profile:

  + 0 = constant velocity.
  
  + 1 = logarithmic velocity.
  
  + 2 = Gaussian velocity.
  
+ C: indicates the task (1-8) of the human mouse database in which the trayectory was synthetized. This is necessary because the function-based method needs the initial [*x̂<sub>1</sub>, ŷ<sub>1</sub>*] and the end [*x̂<sub>M</sub>, ŷ<sub>M</sub>*] points of the human trayectory to synthetyse.

## License Agreement
By downloading the datasets you agree to the following terms and conditions:

+ The DigitWdb and GenderWdb datasets are available for non-commercial research and educational purposes only.
+ You agree not to reproduce, duplicate, copy, sell, trade, resell or exploit for any commercial purposes, any portion of the models and any portion of derived data.
+ BiDA-lab makes no representations or warranties of any kind regarding the Databases, whether express, implied, statutory, or other.
+ You accept full responsibility for your use of the Databases and shall defend and indemnify the BiDA-lab, including their employees, Trustees, officers and agents, against any and all claims arising from your use of the Databases.
+ You may provide research associates and colleagues with access to the Databases provided that they first agree to be bound by these terms and conditions.
+ If you are employed by a for-profit, commercial entity, your employer shall also be bound by these terms and conditions, and you hereby represent that he or she is fully authorized to enter into this agreement on behalf of such employer.

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.

## REFERENCES
For further information on the benchmark and on different applications where it has been used, we refer the reader to (all these articles are publicly available in the [publications](http://atvs.ii.uam.es/atvs/listpublications.do) section of the BiDA group webpage).

+ [1] A. Acien, A. Morales, J. Fierrez, R. Vera-Rodriguez. BeCAPTCHA-Mouse: Synthetic Mouse Trajectories and Improved Bot Detection. *arXiv:2005.00890*, 2020. [[pdf](https://arxiv.org/pdf/2005.00890.pdf)]

+ [2] C. Shen, Z. Cai, X. Guan, R. Maxion. Performance evaluation of anomalydetection algorithms for mouse dynamics, *Computers & Security*, 45: 156–171, 2014.

+ [3] M. Djioua, R. Plamondon. A new algorithm and system for the characterization of handwriting strokes with delta-lognormal parameters, *IEEE Transactions on Pattern Analysis and Machine Intelligence*, 31(11): 2060–2072, 2009.

Please remember to reference article [1] on any work made public, whatever the form, based directly or indirectly on any part of the BeCAPTCHA-Mouse benchmark.
