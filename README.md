# DA626  Team 21  "UniCDR"
### Universal Cross Domain Recommendation
<p>
1st Ankita Anand
Roll-210150006
Data Science and
Artificial Intelligence
<br>
2nd Chhandam Pal
Roll-210121020
Engineering Physics
<br>
3rd Anjum Ulazim
Roll-210121011
Engineering Physics
  </p>
<br>


UniCDR
===


Requirements
---

See requirement.txt

### Datasets

They release a large-scale dataset for multi-domain recommendation in this work, and the all used datasets can be downloaded at [WSDM2023-UniCDR-datasets](https://drive.google.com/drive/folders/1DCYiFU6GCVj681GKYUY2d_BJFln1-8gL?usp=share_link) (including 4 CDR scenarios: dual-user-intra, dual-user-inter, multi-item-intra, and multi-user-intra).

Note that all datasets are required to unzip in the root directory.

Usage
---

To run this project, please make sure that you have the following packages and datasets being downloaded. Our experiments are conducted on a PC with an Intel Xeon E5 2.1GHz CPU, 256 RAM and a Tesla T4 16GB GPU. 

Running example:

```shell
# dual-user-intra
CUDA_VISIBLE_DEVICES=0 python -u train_rec.py  --static_sample --cuda --domains sport_cloth --aggregator user_attention  > dual_user_intra_sport_cloth.log 2>&1&

# dual-user-inter
CUDA_VISIBLE_DEVICES=1 python -u train_rec.py  --static_sample --cuda --domains game_video --task dual-user-inter --aggregator mean > dual_item_inter_game_video.log 2>&1&


# multi-item-intra
CUDA_VISIBLE_DEVICES=2 python -u train_rec.py  --static_sample --cuda --domains m1_m2_m3_m4_m5 --task multi-item-intra --aggregator item_similarity > multi_item_intra.log 2>&1&


# multi-user-intra
CUDA_VISIBLE_DEVICES=3 python -u train_rec.py --static_sample --cuda --domains d1_d2_d3 --task multi-user-intra --aggregator mean > multi_user_intra.log 2>&1&
```

For running Inference Code, just run the cells of these jupyter notebooks-
```shell
#dual-user-intra
inference_dual_user_inter_recommendation.ipynb

# dual-user-inter
inference_dual_user_intra_recommendation.ipynb

# multi-item-intra
inference_multi_item_intra_recommendation.ipynb

# multi-user-intra
inference_multi_user_intra_recommendation.ipynb

```
