# Paper Review - Day 02

## **Paper Title**: Fast Segment Anything
- **Authors**: Yinzhi Cao, Junfeng Yang
- **arXiv**: https://arxiv.org/pdf/2306.12156.pdf
- **Github**: https://github.com/CASIA-IVA-Lab/FastSAM

---

![](./figs/002/1.png)
---


## 🧾 Summary: 
The paper proposes a faster alternative method for the segment anything model (SAM).This method achieves comparable performance with SAM at 50x🔥 higher run-time speed.

## 🚀 Why Faster?
1. FastSAM breaks the segmenting process into two tasks: mask and bounding box creation using a CNN, and filtering based on input in a task-oriented post-processing stage.
2. Firstly, it uses smaller CNNs. Also, it uses a modified YOLOv-8 head instead of ViT, allowing parallel workspace for both the Detection Head and Segmentation head, it reduces computation time. Utilizing CNN properties like local connections and receptive field object assignment, it preserves spatial details with semantic data.
![](./figs/002/2.jpg)

## 📊 Comparison with SAM:
1. Anomaly Detection: lower precision compared to SAM, but can accurately segment using foreground/background points or box-guided selection.
2.  Salient Object Segmentation: only a minor difference from SAM
3. Building Detection: Segments fewer regions related to shadows compared to SAM
![](./figs/002/3.jpg)

## 👎 Weaknesses:
1. Use of YOLACT method, as it is weak in mask generation.

## ⭐ Possibilities:
1. In around 5-6 days, official code repo on GitHub got 4.6K stars!
2. To improve scalability, an additional production trick is suggested where the high processing load for generating masks and bounding boxes is shifted to the server, while the client's machine handles the lightweight filtering process. This leverages the advantages of FastSAM's decoupled architecture.

