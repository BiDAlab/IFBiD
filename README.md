# 

# Databases for Inference-Free Bias Detection (IFBiD)
The Databases contain 48K and 36K TF-Keras models for the digit (DigitWdb) and gender (GenderWdb) classification tasks, with their parameters stored in .h5 file format.

## DigitWdb and GenderWdb Databases

+ Download [DigitWdb](http://atvs.ii.uam.es/atvs/intranet/free_DB/beCAPTCHA).

+ Download [GenderWdb](http://atvs.ii.uam.es/atvs/intranet/free_DB/beCAPTCHA).

We have created two databases to experiment with automatic bias detection: DigitWdb and GenderWdb. The databases contain the weights Ω of the models φ(·,|Ω) used
in our experiments for the digit and gender classification taks. 

## DigitWdb: 48K digit classification networks

**• Train:** 40K models classified by bias level into four groups, with 10K models per level. The models were trained using the first 30K training digits from [Colored MNIST](https://github.com/feidfoe/learning-not-to-learn). Groups are: very high bias (color jitter variance of 0.02), high bias (color jitter variance of 0.03), low bias (color jitter variance of 0.04), and very low bias (color jitter variance of 0.05).

**• Test:** 8K models classified by bias level into four groups (2K models for each level). The models were trained using the last 30K training digits from [Colored MNIST](https://github.com/feidfoe/learning-not-to-learn) and categorized in the same way as the training ones (i.e., from very high bias to very low bias).

*The digits for Train and for Test belong to independent sets.*

**Average digit classification accuracy in DigitWdb models according to their level of bias. The more bias, the worse the classification accuracy of each digit.**
<table>
  <tr align="center">
    <th rowspan="2">Model Bias</th>
    <th colspan="10">Digit Classification Accuracy (%)</th>
  </tr>
   <tr align="center">
    <th>0<th>1<th>2<th>3<th>4<th>5<th>6<th>7<th>8<th>9
  </tr>
  <tr align="center"><td align="left">Very Low	 <td>	88  <td> 94 <td> 77 <td> 82 <td> 90 <td> 89 <td> 75 <td> 84 <td> 81 <td> 82 </tr>
  <tr align="center"><td align="left">Low	      <td>	79  <td>  85  <td>  67  <td>  69  <td>  81  <td>  83  <td>  65  <td>  76  <td>  72  <td>  69 </tr>
  <tr align="center"><td align="left">High	     <td>	66  <td>  76  <td>  54  <td>  56  <td>  72  <td>  69  <td>  49  <td>  64  <td>  58  <td>  46	</tr>
  <tr align="center"><td align="left">Very High	<td>	49  <td>  51  <td>  42  <td>  38  <td>  59  <td>  40  <td>  40  <td>  51  <td>  43  <td>  32 </tr>
</table>


## GenderWdb: 36K gender classification networks

**• Train:** 30K models belonging to three classes of bias, with 10K models per class. Models were trained with the [DiveFace](https://github.com/BiDAlab/DiveFace) database of face images. Bias was introduced by unbalancing each ethnic group during training: aAsian, African/Indian, and Caucasian.

**• Test:** 6K models belonging to three classes of bias. Models were trained and biased using face images from [DiveFace](https://github.com/BiDAlab/DiveFace) in the same way as the Train set.

*The face images for Train and for Test belong to independent sets.*

**Average gender classification accuracy in GenderWdb models according to their class bias.**
<table>
  <tr align="center">
    <th rowspan="2">Model Bias</th>
    <th colspan="10">Gender Classification Accuracy (%)</th>
  </tr>
   <tr align="center">
    <th>Asian<th>African/Indian<th>Caucasian
  </tr>
  <tr align="center"><td align="left">Asian	 <td>	89.5  <td> 81.5 <td> 82.9 </tr>
  <tr align="center"><td align="left">African/Indian	      <td>	82.0  <td>  89.4  <td>  83.0  </tr>
  <tr align="center"><td align="left">Caucasian	     <td>	80.0  <td>  83.2  <td>  89.2  </tr>
</table>

<!-- ![](https://github.com/BiDAlab/BeCAPTCHA-Mouse/blob/master/Fig5.png) -->

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

+ I. Serna, D. DeAlcala, A. Morales, J. Fierrez, and J. Ortega-Garcia. IFBiD: Inference-Free Bias Detection. In *AAAI Workshop on Artificial Intelligence Safety (SafeAI)*, 2022.

Please remember to reference the article on any work made public, whatever the form.
