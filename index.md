<div align="center">
  <h1 align="center">Visualizing Conditioning Signal Influence in ControlNet: A Hybrid Approach</h1>
  <p align="center">
    <a href="mailto:zheng.junx@northeastern.edu">Junxin Zheng</a>¹, <a href="mailto:wang.zhen3@northeastern.edu">Wang Zhen</a>¹
  </p>
  <p align="center">
    ¹<a href="https://khoury.northeastern.edu/">Northeastern University</a>
  </p>
</div>

## Related Work

This project builds upon two primary foundations in the field of controlled image generation with diffusion models. 

First, we leverage the **ControlNet** architecture proposed by Zhang et al. [[1]](#ref1) which introduces a trainable copy of the UNet encoder blocks that allows conditioning signals (such as edges, poses, or segmentation maps) to guide the image generation process. ControlNet has demonstrated remarkable ability to maintain fidelity to input conditions while preserving the high-quality generation capabilities of pretrained diffusion models.

Our work is also heavily inspired by the recent advances in distillation techniques for diffusion models presented by Gandikota and Bau [[2]](#ref2). Their work introduces the concept of Diffusion Target (DT) visualization, which provides insights into what the model predicts as the final output at each intermediate denoising step. This visualization technique has proven invaluable for understanding how different models construct their outputs over time and has directly influenced our development of the hybrid-net approach described in this blog.

Our contribution builds on these foundations by analyzing how conditioning signals influence the denoising trajectory and proposing a novel switching mechanism between specialized and general models to optimize both conditioning fidelity and generation diversity/efficiency.

## Visual Analysis of Denoising Processes

<figure>
  <div align="center">
    <img src="./img/visualization_grid.png" alt="Comparison grid showing Standard Denoising vs DT Visualization at different completion percentages for various conditioning types" width="1200" height="300">
    <figcaption style="text-align: center; color: #000080; font-size: 0.8em;">
      <strong>Figure 1:</strong> Comparison between standard denoising process (left) and Diffusion Target visualization (right) at different timesteps (0%, 30%, 60%, 100%) for three conditioning types: Canny edge, Open Pose, and Segmentation maps. DT-Visualization lets us see what the model predicts as the final output at each intermediate step. This helps us understand how different models build their images over time and reveals key differences between fast and slow models.
    </figcaption>
  </div>
</figure>

Figure 2 reveals fascinating insights into how conditioning signals influence the generation process. The left side shows traditional denoising progression, where the image gradually emerges from random noise. The right side displays DT-Visualization results, showing how the model "sees" the target image at different timesteps.
Notably, DT-Visualization produces recognizable images much earlier in the process. For example, with canny edge detection (top row), we can see a clear image of "Girl with a Pearl Earring" at just 30% completion in the DT visualization, while the standard denoising still shows mostly noise. This suggests that the conditioning signal provides strong guidance early in the process.

## References

<a id="ref1">[1]</a> Zhang, L., Rao, A., & Agrawala, M. (2023). Adding Conditional Control to Text-to-Image Diffusion Models. *arXiv preprint arXiv:2302.05543*. https://doi.org/10.48550/arXiv.2302.05543

<a id="ref2">[2]</a> Gandikota, R., & Bau, D. (2025). Distilling Diversity and Control in Diffusion Models. *arXiv preprint arXiv:2503.10637*. https://distillation.baulab.info/