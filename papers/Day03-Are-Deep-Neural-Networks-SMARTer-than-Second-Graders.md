# Paper Review - Day 03

## **Paper Title**: Are Deep Neural Networks SMARTer than Second Graders?
- **Authors**: Anoop Cherian, Kuan-Chuan Peng, Suhas Lohit, Kevin A. Smith, Joshua B. Tenenbaum
- **Publication**: CVPR 2023
- **arXiv**: https://arxiv.org/abs/2212.09993
- **Github**: https://github.com/merlresearch/SMART
- **Papers with Code**: https://paperswithcode.com/paper/are-deep-neural-networks-smarter-than-second

---

## 🧾 Summary: 
The paper proposes a faster alternative method for the segment anything model (SAM).This method achieves comparable performance with SAM at 50x🔥 higher run-time speed.

## 🚀 Why Faster?
1. FastSAM breaks the segmenting process into two tasks: mask and bounding box creation using a CNN, and filtering based on input in a task-oriented post-processing stage.
2. Firstly, it uses smaller CNNs. Also, it uses a modified YOLOv-8 head instead of ViT, allowing parallel workspace for both the Detection Head and Segmentation head, it reduces computation time. Utilizing CNN properties like local connections and receptive field object assignment, it preserves spatial details with semantic data.

## 📊 Comparison with SAM:
1. Anomaly Detection: lower precision compared to SAM, but can accurately segment using foreground/background points or box-guided selection.
2.  Salient Object Segmentation: only a minor difference from SAM
3. Building Detection: Segments fewer regions related to shadows compared to SAM

## 👎 Weaknesses:
1. Use of YOLACT method, as it is weak in mask generation.

## ⭐ Possibilities:
1. In around 5-6 days, official code repo on GitHub got 4.6K stars!
2. To improve scalability, an additional production trick is suggested where the high processing load for generating masks and bounding boxes is shifted to the server, while the client's machine handles the lightweight filtering process. This leverages the advantages of FastSAM's decoupled architecture.

