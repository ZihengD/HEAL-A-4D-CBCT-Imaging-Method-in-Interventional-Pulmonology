# HEAL: A 4D CBCT Imaging Method in Interventional Pulmonology with Hierarchical Explicit Alignment and Residual Learning

Author: Ziheng Deng, Jun Zhao, School of BME, Shanghai Jiao Tong University

This repository presents the visualization results of HEAL: A 4D CBCT Imaging Method in Interventional Pulmonology with Hierarchical Explicit Alignment and Residual Learning. In this paper, we introduce intraprocedural 4D CBCT imaging for pulmonary interventions. From a single routine CBCT scan, without changing the acquisition protocol, our framework estimates the respiratory signal with RIDE and reconstructs phase-resolved 4D CBCT images with HEAL.

More details will be released after the paper is published.

## Demo

Here are some examples of HEAL tested on __*real clinical intraprocedural CBCT scans*__. The data were acquired with a C-arm CBCT system during ventilator-assisted breathing. Each scan covers 180° in 30 s.

*Note: All visualizations are copyright protected. Contact the author for high-resolution versions or reuse permissions.*

### Reconstruction results in axial view

The two-frame GIFs switch between the averaged image and the HEAL result to show the reduction of motion artifacts. The reference images were acquired in a separate scan with ventilation suspended at deep inspiration.

<p align=center>
<img width="2.9%" src="demo/labels/fig1-corner.png">
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig1-h1-dark.png"><img width="25.1%" src="demo/labels/fig1-h1.png"></picture>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig1-h2-dark.png"><img width="25.1%" src="demo/labels/fig1-h2.png"></picture>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig1-h3-dark.png"><img width="25.1%" src="demo/labels/fig1-h3.png"></picture><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig1-case1-dark.png"><img width="2.9%" src="demo/labels/fig1-case1.png"></picture>
<img width="25.1%" src="demo/fig1-1-1.jpg">
<img width="25.1%" src="demo/fig1-1-2.gif">
<img width="25.1%" src="demo/fig1-1-3.jpg"><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig1-case2-dark.png"><img width="2.9%" src="demo/labels/fig1-case2.png"></picture>
<img width="25.1%" src="demo/fig1-2-1.jpg">
<img width="25.1%" src="demo/fig1-2-2.gif">
<img width="25.1%" src="demo/fig1-2-3.jpg"><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig1-case3-dark.png"><img width="2.9%" src="demo/labels/fig1-case3.png"></picture>
<img width="25.1%" src="demo/fig1-3-1.jpg">
<img width="25.1%" src="demo/fig1-3-2.gif">
<img width="25.1%" src="demo/fig1-3-3.jpg">
</p>

### Dynamic results in coronal view

The two-frame GIFs compare the averaged image with the HEAL result, and the dynamic images show the HEAL reconstruction over a respiratory cycle. MIP denotes maximum intensity projection.

<p align=center>
<img width="2.8%" src="demo/labels/fig2-corner.png">
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig2-h1-dark.png"><img width="18.7%" src="demo/labels/fig2-h1.png"></picture>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig2-h2-dark.png"><img width="18.7%" src="demo/labels/fig2-h2.png"></picture>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig2-h3-dark.png"><img width="18.7%" src="demo/labels/fig2-h3.png"></picture>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig2-h4-dark.png"><img width="18.7%" src="demo/labels/fig2-h4.png"></picture><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig2-case1-dark.png"><img width="2.8%" src="demo/labels/fig2-case1.png"></picture>
<img width="18.7%" src="demo/fig2-1-1.gif">
<img width="18.7%" src="demo/fig2-1-2.gif">
<img width="18.7%" src="demo/fig2-1-3.gif">
<img width="18.7%" src="demo/fig2-1-4.gif"><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig2-case2-dark.png"><img width="2.8%" src="demo/labels/fig2-case2.png"></picture>
<img width="18.7%" src="demo/fig2-2-1.gif">
<img width="18.7%" src="demo/fig2-2-2.gif">
<img width="18.7%" src="demo/fig2-2-3.gif">
<img width="18.7%" src="demo/fig2-2-4.gif"><br>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig2-case3-dark.png"><img width="2.8%" src="demo/labels/fig2-case3.png"></picture>
<img width="18.7%" src="demo/fig2-3-1.gif">
<img width="18.7%" src="demo/fig2-3-2.gif">
<img width="18.7%" src="demo/fig2-3-3.gif">
<img width="18.7%" src="demo/fig2-3-4.gif">
</p>

### Dynamic augmented fluoroscopy

4D CBCT may also support downstream applications such as dynamic augmented fluoroscopy. This is a conceptual demonstration, in which the red masks indicate the lesion positions on the 4D CBCT images and on the fluoroscopic projections during breathing.

<p align=center>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig3-h1-dark.png"><img width="39.7%" src="demo/labels/fig3-h1.png"></picture>
<picture><source media="(prefers-color-scheme: dark)" srcset="demo/labels/fig3-h2-dark.png"><img width="39.7%" src="demo/labels/fig3-h2.png"></picture><br>
<img width="39.7%" src="demo/fig3-1-1.gif">
<img width="39.7%" src="demo/fig3-1-2.gif">
</p>

## Workflow

### Respiratory signal estimation with RIDE

RIDE (Respiratory Implicit Decomposition and Encoding) estimates the respiratory signal from CBCT projections by separating respiratory patterns from non-respiratory interference.

<div align=center><img width="1080" src="demo/fig_RIDE.png"></div>

### 4D CBCT reconstruction with HEAL

HEAL first recovers major anatomical structures through explicit inter-phase alignment, and then progressively refines local details through residual learning.

<div align=center><img width="1080" src="demo/fig_HEAL.png"></div>
