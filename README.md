# Gaussian Processes for Time Series with PyTorch

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1_uG0memqk_Idj51RvfZ-KtlwQMstgF1X)

![GPyTorch](assets/gp_banner.png)

A hands-on tutorial on fitting Gaussian processes to time series with [GPyTorch](https://gpytorch.ai). The main lesson is that **the kernel is the model**, so most of the work goes into designing the right kernel for the data.

## What is inside

1. A short recap of Gaussian processes
2. The GPyTorch building blocks (model, kernels, training loop)
3. A worked example on the Mauna Loa CO₂ dataset
4. An exercise where you design a kernel for real wireless traffic data from Huawei
5. Automated kernel design with LLMs ([CAKE](https://github.com/richardcsuwandi/cake) and [Kernaut](https://github.com/richardcsuwandi/kernaut)), including the kernel Kernaut discovered for the Huawei data and a 30-cell challenge against it

## How to run

**On Google Colab (recommended).** Click the badge above and choose *Runtime → Run all*. Nothing needs to be installed or uploaded.

**On your own machine.** Clone the repository, install the packages, and open the notebook.

```bash
git clone https://github.com/richardcsuwandi/gp-time-series-tutorial.git
cd gp-time-series-tutorial
pip install torch gpytorch scikit-learn pandas matplotlib ipywidgets jupyter
jupyter notebook gp_time_series_tutorial.ipynb
```

## Data

* **Mauna Loa CO₂.** Downloaded automatically from OpenML inside the notebook.
* **Huawei wireless traffic** ([`huawei_cell_traffic.csv`](huawei_cell_traffic.csv)). Uplink traffic of 30 anonymized wireless network cells, recorded every 5 minutes for 7 days (2024-11-30 to 2024-12-07). The notebook loads it straight from this repository.

## References

**Documentation**

* [PyTorch documentation](https://docs.pytorch.org/docs/stable/index.html)
* [GPyTorch documentation](https://docs.gpytorch.ai/en/stable/), including the [simple GP regression example](https://docs.gpytorch.ai/en/stable/examples/01_Exact_GPs/Simple_GP_Regression.html)
* [scikit-learn Mauna Loa CO₂ example](https://scikit-learn.org/stable/auto_examples/gaussian_process/plot_gpr_co2.html)

**Background reading**

1. C. E. Rasmussen and C. K. I. Williams. *Gaussian Processes for Machine Learning*. MIT Press, 2006. [[Free online book]](https://gaussianprocess.org/gpml/)
2. J. R. Gardner, G. Pleiss, D. Bindel, K. Q. Weinberger, and A. G. Wilson. GPyTorch: Blackbox matrix-matrix Gaussian process inference with GPU acceleration. In *Advances in Neural Information Processing Systems (NeurIPS)*, 2018. [[Paper]](https://arxiv.org/abs/1809.11165)

**Automated kernel design with LLMs**

3. R. C. Suwandi, F. Yin, J. Wang, R. Li, T.-H. Chang, and S. Theodoridis. Adaptive kernel design for Bayesian optimization is a piece of CAKE with LLMs. In *Advances in Neural Information Processing Systems (NeurIPS)*, 2025. [[Paper]](https://arxiv.org/abs/2509.17998) [[Code]](https://github.com/richardcsuwandi/cake)
4. R. C. Suwandi, F. Yin, and K. Murphy. Kernel autoresearch for open-ended model discovery. *arXiv preprint arXiv:2610.10394*, 2026. [[Paper]](https://arxiv.org/abs/2610.10394) [[Code]](https://github.com/richardcsuwandi/kernaut)
