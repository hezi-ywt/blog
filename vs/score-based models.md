
# score-based model
非常好的score-based model解释blog:https://yang-song.net/blog/2021/score/

$$$$
个人理解：在传统的任务如分类，我们模型最后输出的概率中的X对应的是类别，而这些类别就是猫、狗之类的标签，数量有限，很容易满足概率归一化，而生成模型的x对应的是生成物，这些生成物的空间是难以计算的，比如生成一个脸，少一根头发都算一个新的样本，而相差几百几千根头发的样本都是满意的结果，这个概率要归一化就比较麻烦，一方面计算总体麻烦，另一方面满意的样本会很多，分到的概率值会比较低。


$$\int_X p_\theta(x)=1   $$
一个概率的常识，但是在生成模型中是个很头疼的限制
$$energe\ based:\ p_\theta(x)=\frac{f_\theta(x)}{Z_\theta}$$

### score function

浅看score function是为了摆脱概率定义的限制, 因为 $$s_\theta(x)\sim\nabla_xlogP(x)$$它是没有积分限制的。

### Score matching objectives
$$E_{x}[||\nabla_xlogp(x)-s_\theta(x)||_2^2]$$
### Langevin dynamics
$$x_{i+1}=x_i+\epsilon\nabla_xlogp(x)+\sqrt{2\epsilon}z_i$$

### Score-based generative modeling with multiple noise perturbations