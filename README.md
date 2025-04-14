# Extending Stable Diffusion with External Control: Revisiting ControlNet
> Authors: Junxin (Gin) Zheng, Zhen Wang 

In this project, we investigate the dynamics of image conditioning in ControlNet using Diffusion Target Visualization (DT-Visualization) as a central analytical tool. By applying DT-Visualization to the ControlNet framework, we explore how conditioning signals influence the denoising process at each stage, revealing deeper insights into the model's internal behavior. Building on these insights, we propose a novel hybrid-net approach that strategically switches between ControlNet and standard diffusion models at intermediate timesteps as an attempt to improve inference efficiency. 

Our study also revisits key architectural components of ControlNet, with a particular focus on zero-initialized convolution layers and their role in ensuring stable training and effective conditional control. Additionally, we examine the implementation of classifier-free guidance, analyzing how variations in guidance resolution weighting affect image quality during both training and inference. Together, these investigations provide a comprehensive understanding of conditional control in the ControlNet model.