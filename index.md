<div align="center">
  <h1 align="center">Visualizing Conditioning Signal Influence in ControlNet: A Hybrid Approach</h1>
  <p align="center">
    <a href="mailto:zheng.junx@northeastern.edu">Junxin Zheng</a>¹, <a href="mailto:wang.zhen3@northeastern.edu">Wang Zhen</a>¹
  </p>
  <p align="center">
    ¹<a href="https://khoury.northeastern.edu/">Northeastern University</a>
  </p>
</div>

## Visual Analysis of Denoising Processes

<figure>
  <div align="center">
    <img src="./img/visualization_grid.png" alt="Comparison grid showing Standard Denoising vs DT Visualization at different completion percentages for various conditioning types" width="1200" height="400">
    <figcaption style="text-align: center; color: #0066cc; max-width: 800px; margin: 0 auto;">
      <strong>Figure 1:</strong> Comparison between standard denoising progression (left) and Diffusion Target visualization (right) at different timesteps (0%, 30%, 60%, 100%) for three conditioning types: Canny edge detection, Pose estimation, and Segmentation maps. DT-Visualization lets us see what the model predicts as the final output at each intermediate step. This helps us understand how different models build their images over time and reveals key differences between fast and slow models.
    </figcaption>
  </div>
</figure>

Figure 2 reveals fascinating insights into how conditioning signals influence the generation process. The left side shows traditional denoising progression, where the image gradually emerges from random noise. The right side displays DT-Visualization results, showing how the model "sees" the target image at different timesteps.
Notably, DT-Visualization produces recognizable images much earlier in the process. For example, with canny edge detection (top row), we can see a clear image of "Girl with a Pearl Earring" at just 30% completion in the DT visualization, while the standard denoising still shows mostly noise. This suggests that the conditioning signal provides strong guidance early in the process.