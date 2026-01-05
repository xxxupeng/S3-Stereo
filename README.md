<h2 align="center">

Unsupervised Stereo via Multi-Baseline Geometry-Consistent Self-Training<br>

[Project Page]() ｜ [Paper](https://arxiv.org/abs/2508.10838) 

</h2> 

<img src="./assets/teaser5.png" alt="Alt text" style="width: 800px;" title="architecture">

<p style="text-align: justify;"><strong>Top.</strong> Illustration of learning behaviors in occluded regions: (a) Photometric loss takes a shortcut by copying disparities from nearby visible areas; (b) Occlusion-masked photometric loss (masked-PL) fails to supervise occlusion completion, leaving these regions poorly estimated; (c) Our S$^3$ accurately predicts disparities even in heavily occluded areas. <strong>>Bottom.</strong> S$^3$ achieves outstanding unsupervised performance on the (d) KITTI 2015 and (e) KITTI 2012 benchmarks, as well as zero-shot generalization in (f).


## :clapper: Introduction
Photometric loss and pseudo-label-based self-training are two widely used methods for training stereo networks on unlabeled data.
However, they both struggle to provide accurate supervision in occluded regions. The former lacks valid correspondences, while the latter’s pseudo labels are often unreliable.
To overcome these limitations, we present S$^3$, a simple yet effective framework based on multi-baseline geometry consistency.
Unlike conventional self-training where teacher and student share identical stereo pairs, S$^3$ assigns them different target images, introducing natural visibility asymmetry. Regions occluded in the student’s view often remain visible and matchable to the teacher, enabling reliable pseudo labels even in regions where photometric supervision fails. The teacher’s disparities are rescaled to align with the student's baseline and used to guide student learning. An occlusion-aware weighting strategy is further proposed to mitigate unreliable supervision in teacher-occluded regions and to encourage the student to learn robust occlusion completion. To support training, we construct MBS20K, a multi-baseline stereo dataset synthesized using the CARLA simulator. Extensive experiments demonstrate that S$^3$ provides effective supervision in both occluded and non-occluded regions, achieves strong generalization performance, and surpasses previous state-of-the-art methods on the KITTI 2015 and 2012 benchmarks.

**Contributions:** 

* We propose a novel asymmetric unsupervised training framework for stereo matching that leverages multi-baseline geometry consistency to enable effective supervision in occluded regions.

* We introduce an occlusion-aware weighting mechanism that emphasizes teacher-visible but student-occluded regions while masking the unreliable teacher-occluded pixels, effectively guiding the learning in both occluded and non-occluded regions.

* Our method achieves state-of-the-art results on the KITTI 2015 and KITTI 2012 benchmarks, significantly outperforming previous unsupervised methods and even surpassing several early supervised methods.

* Our method exhibits excellent generalization to diverse scenes and maintains robust performance under changing weather conditions.


## :memo: Code

coming soon...

## :floppy_disk: Datasets


### MBS20K

You can download our MonoTrap dataset from our [drive]().
