# MNasNet

[1] Mingxing Tan, et al. MnasNet: Platform-Aware Neural Architecture Search for Mobile. CVPR 2019. Arxiv link: https://arxiv.org/pdf/1807.11626.pdf


## About the Model

We provide a few standard-size and small-size AutoML models in [`mnasnet_models.py`](mnasnet_models.py) including:

  * <b>mnasnet-a1</b> has ~75.2% top-1 ImageNet accuracy  with 3.9M parameters and 312M Multiply-Adds.
  * <b>mnasnet-small</b> has ~66% top-1 ImageNet accuracy with 2.0M parameters and 68M Multiply-Adds.

The standard size MnasNet-A1 inference has 1.8x faster throughput (55% lower latency) than the
corresponding MobileNetV2 model.

![MnasNet-A1 and MobileNetV2](g3doc/mnasnet_vs_mobilenetv2_2.png)

Comparing to [MobileNetV2](https://arxiv.org/pdf/1801.04381.pdf),
MnasNet-A1 model has clear better performance in accuracy when they are at the
same latency level.

![MnasNet-A1 and MobileNetV2 Details](g3doc/mnasnet_vs_mobilenetv2.png)


Here are the details of Mnasnet-A1 on ImageNet:

Input Size	| Depth Multiplier	| Top-1 Accuracy | 	Top-5 Accuracy	| Parameters(M)	| Multi-Adds (M)	| Pixel 1 latency (ms)
------- | ---------| --------- |---------|----|------------- | ----
224 |	1.4	| 77.2	| 93.5 |	6.1	|  591.5	| 135| 	77.2
224 |	1	  | 75.2	| 92.5 |	3.9	|  315.2	| 78	| 75.2
224 |	0.75| 73.3	| 91.3 |	2.9	|  226.7	| 61	| 73.3
224 |	0.5	| 68.9	| 88.4 |	2.1	|  105.2	| 32	| 68.9
224 |	0.35| 64.1	| 85.1 |	1.7	|  63.2	 |  22| 	64.1
192 |	1.4	| 76.1	| 93.0 |	6.1	|  435.1	| 99	| 76.1
192 |	1	  | 74.0	| 91.6 |	3.9	|  232.0	| 57	| 74
192 |	0.75| 72.1	| 90.5 |	2.9	|  166.9	| 45	| 72.1
192 |	0.5	| 67.2	| 87.4 |	2.1	|  77.6	 |  24| 	67.2
192 |	0.35| 62.4	| 83.8 |	1.7	|  46.8	 |  17| 	62.4
160 |	1.4	| 74.8	| 92.1 |	6.1	|  302.8	| 72	| 74.8
160 |	1	  | 72.0	| 90.5 |	3.9	|  161.6	| 41	| 72
160 |	0.75| 70.1	| 89.3 |	2.9	|  116.4	| 33	| 70.1
160 |	0.5	| 64.9	| 85.8 |	2.1	|  54.4	 |  18| 	64.9
160 |	0.35| 52.3	| 81.5 |	1.7	|  32.9	 |  13| 	59.3
128 |	1.4	| 72.5	| 90.6 |	6.1	|  194.5	| 49	| 72.5
128 |	1	  | 69.3	| 88.9 |	3.9	|  104.1	| 29	| 69.3
128 |	0.75| 67.0	| 87.3 |	2.9	|  75.0	 |  23| 	67
128 |	0.5	| 60.8	| 83.0 |	2.1	|  35.3	 |  12| 	60.8
128 |	0.35| 54.8	| 78.1 |	1.7	|  21.6	 |  8.5|	54.8
96	 |1.4	| 68.6	| 88.1 |  6.1	|  110.3	| 32	| 68.6
96	 |1	  | 64.4	| 85.8 |  3.9	|  59.3	 |  18| 	64.4
96	 |0.75| 62.1	| 84.0 |  2.9	|  42.9	 |  17| 	62.1
96	 |0.5	| 54.7	| 78.1 |  2.1	|  20.5	 |  7.4 | 54.7
96	 |0.35| 49.3	| 73.4 |	1.7	|  12.7	  | 5.4| 	49.3

For more information about training, please refer to our tutorial: https://cloud.google.com/tpu/docs/tutorials/mnasnet