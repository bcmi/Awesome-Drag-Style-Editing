# Awesome Drag-Style Editing [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A curated list of resources including papers, datasets, and relevant links pertaining to drag-style image editing. **Drag-style editing aims to manipulate image content according to user-specified dragging conditions, which can be categorized into point-based drag and region-based drag.** In point-based drag, users provide pairs of handle points and target points to specify how image content should move. In region-based drag, users provide a source region mask and a target region mask, offering denser and more precise control that substantially reduces ambiguity.

## Contributing

Contributions are welcome. If you wish to contribute, feel free to send a pull request. If you have suggestions for new sections to be included, please raise an issue and discuss before sending a pull request.

## Table of Contents

- [Papers](#papers)
  - [Point-based Drag](#point-based-drag)
    - [Iterative Optimization Methods](#iterative-optimization-methods)
    - [Single-step / Feed-forward Methods](#single-step--feed-forward-methods)
  - [Region-based Drag](#region-based-drag)
- [Datasets](#datasets)
- [Other Resources](#other-resources)

---

## Papers

### Point-based Drag

In point-based drag, users provide pairs of handle points and target points. The model moves the content at handle points toward the target points while preserving the rest of the image. Methods are divided into those that rely on iterative latent optimization at inference time, and those that complete editing in a single forward pass.

#### Iterative Optimization Methods

These methods iteratively update the noisy latent or model parameters at inference time via motion supervision and point tracking.

- Siwei Xia, Li Sun, Tiantian Sun, Qingli Li: "DragLoRA: Online Optimization of LoRA Adapters for Drag-based Image Editing in Diffusion Model." ICML (2025) [[arXiv](https://arxiv.org/abs/2505.12427)] [[paper](https://openreview.net/pdf?id=b74kufhhsk)] [[code](https://github.com/Sylvie-X/DragLoRA)]
- Delong Chen, Bo Chen, Yuge Geng, Liang Bo: "AdaptiveDrag: Semantic-Driven Dragging on Diffusion-Based Image Editing." arXiv:2410.12696 (2024) [[arXiv](https://arxiv.org/abs/2410.12696)] [[code](https://github.com/Calvin11311/AdaptiveDrag)]
- Zhanghan Ke, Qianru Sun, Jiankang Deng, Yi Xu, Gang Hua: "CLIPDrag: Combining Text-based and Drag-based Instructions for Image Editing." arXiv:2410.03097 (2024) [[arXiv](https://arxiv.org/abs/2410.03097)] [[code](https://github.com/ZiQi-Jiang/CLIPDrag)]
- Zewei Zhang, Huan Liu, Jun Chen, Xiangyu Xu: "GoodDrag: Towards Good Practices for Drag Editing with Diffusion Models." NeurIPS (2024) [[arXiv](https://arxiv.org/abs/2404.07206)] [[paper](https://openreview.net/pdf?id=VtYfbvwpWp)] [[code](https://github.com/zewei-Zhang/GoodDrag)] [[project](https://gooddrag.github.io/)] [[demo](https://colab.research.google.com/drive/1eoX-AngrcHocLKAgL5g5fyseLW_DusWl?usp=sharing)]
- Yutao Cui, Xiaotong Zhao, Guozhen Zhang, Shengming Cao, Kai Ma, Limin Wang: "StableDrag: Stable Dragging for Point-based Image Editing." ECCV (2024) [[arXiv](https://arxiv.org/abs/2403.04437)] [[paper](https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/07572.pdf)] [[project](https://stabledrag.github.io/)]
- Haofeng Liu, Chenshu Xu, Yifei Yang, Lihua Zeng, Shengfeng He: "Drag Your Noise: Interactive Point-based Editing via Diffusion Semantic Propagation." CVPR (2024) [[arXiv](https://arxiv.org/abs/2404.01050)] [[paper](https://openaccess.thecvf.com/content/CVPR2024/papers/Liu_Drag_Your_Noise_Interactive_Point-based_Editing_via_Diffusion_Semantic_Propagation_CVPR_2024_paper.pdf)] [[code](https://github.com/haofengl/DragNoise)]
- Xingzhong Hou, Boxiao Liu, Yi Zhang, Jihao Liu, Yu Liu, Haihang You: "EasyDrag: Efficient Point-based Manipulation on Diffusion Models." CVPR (2024) [[paper](https://openaccess.thecvf.com/content/CVPR2024/papers/Hou_EasyDrag_Efficient_Point-based_Manipulation_on_Diffusion_Models_CVPR_2024_paper.pdf)] [[code](https://github.com/Ace-Pegasus/EasyDrag)]
- Pengyang Ling, Lin Chen, Pan Zhang, Huaian Chen, Yi Jin, Jinjin Zheng: "FreeDrag: Feature Dragging for Reliable Point-based Image Editing." CVPR (2024) [[arXiv](https://arxiv.org/abs/2307.04684)] [[paper](https://openaccess.thecvf.com/content/CVPR2024/papers/Ling_FreeDrag_Feature_Dragging_for_Reliable_Point-based_Image_Editing_CVPR_2024_paper.pdf)] [[code](https://github.com/LPengYang/FreeDrag)] [[project](https://lin-chen.site/projects/freedrag/)] [[demo](https://openxlab.org.cn/apps/detail/LPengYang/FreeDrag)]
- Gayoon Choi, Taejin Jeong, Sujung Hong, Jaehoon Joo, Seong Jae Hwang: "DragText: Rethinking Text Embedding in Point-based Image Editing." WACV (2025) [[arXiv](https://arxiv.org/abs/2407.17843)] [[paper](https://openaccess.thecvf.com/content/WACV2025/papers/Choi_DragText_Rethinking_Text_Embedding_in_Point-Based_Image_Editing_WACV_2025_paper.pdf)] [[code](https://github.com/MICV-yonsei/DragText)] [[project](https://micv-yonsei.github.io/dragtext2025/)]
- Yujun Shi, Chuhui Xue, Jun Hao Liew, Jiachun Pan, Hanshu Yan, Wenqing Zhang, Vincent Y. F. Tan, Song Bai: "DragDiffusion: Harnessing Diffusion Models for Interactive Point-based Image Editing." CVPR (2024) [[arXiv](https://arxiv.org/abs/2306.14435)] [[paper](https://openaccess.thecvf.com/content/CVPR2024/papers/Shi_DragDiffusion_Harnessing_Diffusion_Models_for_Interactive_Point-based_Image_Editing_CVPR_2024_paper.pdf)] [[code](https://github.com/Yujun-Shi/DragDiffusion)]
- Chong Mou, Xintao Wang, Jiechong Song, Ying Shan, Jian Zhang: "DragonDiffusion: Enabling Drag-style Manipulation on Diffusion Models." ICLR (2024) [[arXiv](https://arxiv.org/abs/2307.02421)] [[paper](https://openreview.net/pdf?id=OEL4FJMg1b)] [[code](https://github.com/MC-E/DragonDiffusion)]
- Xingang Pan, Ayush Tewari, Thomas Leimkühler, Lingjie Liu, Abhimitra Meka, Christian Theobalt: "Drag Your GAN: Interactive Point-based Manipulation on the Generative Image Manifold." ACM SIGGRAPH (2023) [[arXiv](https://arxiv.org/abs/2305.10973)] [[paper](https://dl.acm.org/doi/epdf/10.1145/3588432.3591500)] [[code](https://github.com/XingangPan/DragGAN)] [[demo](https://huggingface.co/spaces/DragGan/DragGan)]

#### Single-step / Feed-forward Methods

These methods complete editing in a single forward pass by reformulating drag editing as a conditional generation or warping task, eliminating iterative optimization at inference time.

- Zixin Yin, Xili Dai, Duomin Wang, Xianfang Zeng, Lionel M. Ni, Gang Yu, Heung-Yeung Shum: "LazyDrag: Enabling Stable Drag-Based Editing on Multi-Modal Diffusion Transformers via Explicit Correspondence." ICLR (2026) [[arXiv](https://arxiv.org/abs/2509.12203)] [[paper](https://openreview.net/pdf?id=PHipCRoSyh)] [[project](https://lazydrag.github.io/)]
- Jingyi Lu, Kai Han: "Inpaint4Drag: Repurposing Inpainting Models for Drag-Based Image Editing via Bidirectional Warping." ICCV (2025) [[arXiv](https://arxiv.org/abs/2509.04582)] [[code](https://github.com/Visual-AI/Inpaint4Drag)] [[demo](https://colab.research.google.com/drive/1fzoyNzcJNZjM1_08FE9V2V20EQxGf4PH?usp=sharing)] [[project](https://visual-ai.github.io/inpaint4drag/)]
- Joonghyuk Shin, Daehyeon Choi, Jaesik Park: "InstantDrag: Improving Interactivity in Drag-based Image Editing." SIGGRAPH Asia (2024) [[arXiv](https://arxiv.org/abs/2409.08857)] [[paper](https://dl.acm.org/doi/epdf/10.1145/3680528.3687668)] [[code](https://github.com/SNU-VGILab/InstantDrag)] [[project](https://joonghyuk.com/instantdrag-web/)]
- Xuanjia Zhao, Jian Guan, Congyi Fan, Dongli Xu, Youtian Lin, Haiwei Pan, Pengming Feng: "FastDrag: Manipulate Anything in One Step." NeurIPS (2024) [[arXiv](https://arxiv.org/abs/2405.15769)] [[code](https://github.com/XuanjiaZ/FastDrag)] [[project](https://fastdrag-site.github.io/)]
- Yujun Shi, Jun Hao Liew, Hanshu Yan, Vincent Y. F. Tan, Jiashi Feng: "LightningDrag: Lightning Fast and Accurate Drag-based Image Editing Emerging from Videos." arXiv:2405.13722 (2024) [[arXiv](https://arxiv.org/abs/2405.13722)] [[code](https://github.com/magic-research/LightningDrag)] [[project](https://lightning-drag.github.io/)] [[demo](https://huggingface.co/spaces/LightningDrag/LightningDrag)]
- Omri Avrahami, Rinon Gal, Gal Chechik, Ohad Fried, Dani Lischinski, Arash Vahdat, Weili Nie: "DiffUHaul: A Training-Free Method for Object Dragging in Images." SIGGRAPH Asia (2024) [[arXiv](https://arxiv.org/abs/2406.01594)] [[paper](https://dl.acm.org/doi/epdf/10.1145/3680528.3687604)] [[project](https://omriavrahami.com/diffuhaul/)]

---

### Region-based Drag

In region-based drag, users provide a source region mask (original location/shape) and a target region mask (desired location/shape), offering denser and more precise control that substantially reduces ambiguity compared with point-based drag.


- Zihan Zhou, Shilin Lu, Shuli Leng, Shaocong Zhang, Zhuming Lian, Xinlei Yu, Adams Wai-Kin Kong: "DragFlow: Unleashing DiT Priors with Region Based Supervision for Drag Editing." ICLR (2026) [[arXiv](https://arxiv.org/abs/2510.02253)] [[paper](https://openreview.net/pdf?id=Zhckizkww1)] [[code](https://github.com/Edennnnnnnnnn/DragFlow)]
- Jingyi Lu, Xinghui Li, Kai Han: "RegionDrag: Fast Region-Based Image Editing with Diffusion Models." ECCV (2024) [[arXiv](https://arxiv.org/abs/2407.18247)] [[paper](https://www.ecva.net/papers/eccv_2024/papers_ECCV/papers/01176.pdf)] [[code](https://github.com/Visual-AI/RegionDrag)] [[project](https://visual-ai.github.io/regiondrag/)] [[demo](https://colab.research.google.com/drive/1pnq9t_1zZ8yL_Oba20eBLVZLp3glniBR?usp=sharing)]
- Naoki Matsunaga, Masato Ishii, Akio Hayakawa, Kenji Suzuki, Takuya Narihira: "Fine-grained Image Editing by Pixel-wise Guidance Using Diffusion Models." arXiv:2212.02024 (2022) [[arXiv](https://arxiv.org/abs/2212.02024)] [[code](https://github.com/sony/pixel-guided-diffusion)]
- Huan Ling, Karsten Kreis, Daiqing Li, Seung Wook Kim, Antonio Torralba, Sanja Fidler: "EditGAN: High-Precision Semantic Image Editing." NeurIPS (2021) [[arXiv](https://arxiv.org/abs/2111.03186)] [[paper](https://proceedings.neurips.cc/paper/2021/file/880610aa9f9de9ea7c545169c716f477-Paper.pdf)] [[project](https://nv-tlabs.github.io/editGAN/)]

---

## Datasets

- **DragBench** — Introduced by DragDiffusion (CVPR 2024). The first benchmark for evaluating point-based drag methods. Contains 211 real images spanning diverse object categories, indoor/outdoor scenes, and artistic styles, with 394 user-annotated handle-target point pairs. Extended by RegionDrag into **DragBench-DR** and **DragBench-SR**, which replace point annotations with region masks for evaluating region-based methods. [[link](https://github.com/Yujun-Shi/DragDiffusion)]
- **Drag100** — Introduced by GoodDrag (NeurIPS 2024). A curated benchmark of 100 drag instructions with two dedicated quality metrics: Dragging Accuracy Index (DAI) evaluating drag precision, and Gemini Score assessing image naturalness and fidelity via large multimodal models. [[link](https://gooddrag.github.io/)]
- **FreeDragBench** — Introduced by FreeDrag (CVPR 2024). Contains 2,251 handmade dragging instructions designed for GAN-based drag evaluation, with a symmetrical dragging accuracy metric. [[link](https://github.com/LPengYang/FreeDrag)]
- **ReD Bench** — Introduced by DragFlow (ICLR 2026). Features region-level dragging instructions for evaluating region-based drag methods, complementing the point-based DragBench. [[link](https://github.com/Edennnnnnnnnn/DragFlow)]

---

## Other Resources

