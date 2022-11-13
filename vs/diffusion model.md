# diffusion model

包含两个过程
- 前向不断给输入添加噪声
- 后向通过不断去噪来学习如何生成

    “Diffusion models are straightforward to define and efficient to train”
    ：https://arxiv.org/pdf/2006.11239.pdf


$$ p_\theta(x_0):=\int{p_\theta(x_{0:T})}dx_{1:T} $$



这里提到KL散度，这是用来衡量两个分布之间差异的常用度量方式
$$D_{KL}(P||Q)=\int{p(x)log\frac{p(x)}{q(x)}}d(x)$$