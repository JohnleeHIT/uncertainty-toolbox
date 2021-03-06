# Metrics

We describe the metrics provided by Uncertainty Toolbox.


## Calibration

### Mathematical Definitions
We focus on the regression setting where the output space is continuous.

#### Notations and Settings
<!--- <img src="https://render.githubusercontent.com/render/math?math="> -->

- <img src="https://render.githubusercontent.com/render/math?math=\mathbf{X, Y}"> are random variables and <img src="https://render.githubusercontent.com/render/math?math=x,y"> are observed values of the random variables.
- Observations for <img src="https://render.githubusercontent.com/render/math?math=\mathbf{Y}"> are always assumed to be conditioned on an observation of <img src="https://render.githubusercontent.com/render/math?math=\mathbf{X}">.
- Dataset <img src="https://render.githubusercontent.com/render/math?math=D = {(x_1, y_1), (x_2, y_2), ..., (x_n, y_n)}">, <img src="https://render.githubusercontent.com/render/math?math=x \in \mathbb{R}^{d}, y \in \mathbb{R}">
- The data is generated by a true underlying distribution, characterized by a CDF <img src="https://render.githubusercontent.com/render/math?math=F(\mathbf{Y|X})">, i.e. <img src="https://render.githubusercontent.com/render/math?math=F(k|x) = p_{\mathbf{Y}|x}(\mathbf{Y} \leq k)">
- The inverse function of this true CDF is the true quantile function, <img src="https://render.githubusercontent.com/render/math?math=Q">, <img src="https://render.githubusercontent.com/render/math?math=F(y|x) = p\Leftrightarrow Q(p|x) = y">
- Uncertainty predictions are expressed as predictions of the quantile function <img src="https://render.githubusercontent.com/render/math?math=\hat{Q}(p|x)">

#### Levels of Calibration



#### Calibration for Classification
> Confidence calibration is "the problem of predicting probability estimates representative of the true correctness likelihood." [(Guo et al., 2017)](https://arxiv.org/pdf/1706.04599.pdf).

Let <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{300}&space;\hat{Y}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{300}&space;\hat{Y}" title="\hat{Y}" /></a> and <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{300}&space;\hat{P}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{300}&space;\hat{P}" title="\hat{P}" /></a> be the predicted class and its associated confidence (probability of correctness). We would like the confidence estimates <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{300}&space;\hat{P}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{300}&space;\hat{P}" title="\hat{P}" /></a> to be calibrated, which intuitively means that we want <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{300}&space;\hat{P}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{300}&space;\hat{P}" title="\hat{P}" /></a> to represent true probabilities (Guo et al., 2017).

<p align="center">
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{300}&space;\mathbb{P}(\hat{Y}=Y&space;\mid&space;\hat{P}=p)=p,&space;\forall&space;p&space;\in[0,1]" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\dpi{300}&space;\mathbb{P}(\hat{Y}=Y&space;\mid&space;\hat{P}=p)=p,&space;\forall&space;p&space;\in[0,1]" title="\mathbb{P}(\hat{Y}=Y \mid \hat{P}=p)=p, \forall p \in[0,1]" /></a>
</p>

Suppose a classification model is given <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{300}&space;N" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{300}&space;N" title="N" /></a> input examples, and made predictions <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{300}&space;\hat{y}_1,&space;...,&space;\hat{y}_N" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{300}&space;\hat{y}_1,&space;...,&space;\hat{y}_N" title="\hat{y}_1, ..., \hat{y}_N" /></a> , each with <a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{300}&space;\hat{p}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{300}&space;\hat{p}" title="\hat{p}" /></a> = `0.35`. We would expect `35%` of the predictions would be correct.
