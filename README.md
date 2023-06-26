# Deep Fashion3D: A Dataset and Benchmark for 3D Garment Reconstruction from Single Images (ECCV 2020)

  <p align="center">
    <a href="https://people.mpi-inf.mpg.de/~hezhu/"><strong>Heming Zhu</strong></a>
    ·
    <a href="https://danielcho-hk.github.io/Daniel-Tsao.github.io/"><strong>Yu Cao</strong></a>
    ·
    <a href="https://gaplab.cuhk.edu.cn/pages/people"><strong>Hang Jin</strong></a>
    ·
    <a href="https://scholar.google.com/citations?hl=zh-CN&user=zYxSLfQAAAAJ&view_op=list_works&sortby=pubdate"><strong>Dong Du</strong></a>
    ·
    <a href="http://www.cad.zju.edu.cn/home/zywang/"><strong>Zhangye Wang</strong></a>
    ·
    <a href="https://sse.cuhk.edu.cn/en/faculty/cuishuguang"><strong>Shuguang Cui</strong></a>
    ·
    <a href="https://gaplab.cuhk.edu.cn/pages/people"><strong>Xiaoguang Han*</strong></a>
  </p>
  
---

# News
**2023-6-25** **Deep Fashion3D V2** is available, where the <strong>dense garment point clouds</strong> are equiped with <strong><font color=red>more accurate feature line annotation</font></strong>, <strong><font color=blue>registered mesh  with category-specific toplogy</font></strong> and <strong><font color=green>high-resolution texture maps</font></strong>! Click     <a href="https://kv2000.github.io/2023/06/18/deepFashion3DV2/"><strong>Here</strong></a> to browse the release note.
**2020-8-24** **Deep Fashion3D** is released with garment models. Feature line annotations and garment pose annotations ~~will be released soon~~ are released. Click     <a href="https://kv2000.github.io/2020/03/25/deepFashion3DRevisited/"><strong>Here</strong></a> to browse the project page.

---

# Download
You may find both **DeepFashion3D** and **Deep Fashion3D V2** in the following link. Please **[fill in the form](https://forms.gle/1SMrPHCyS3m7pkXM6)** to get password for unzipping the compressed file for **DeepFashion3D** and **Deep Fashion3D V2**.

The download link for Deep Fashshion3D V2:  
Google Drive: **[[Google Drive]](https://drive.google.com/drive/folders/1pwCQb4koOAr_Ocuz61ilBm2XPD6QGCu3?usp=sharing)**
Baiduyun Drive: **[[Baidu Drive]](https://pan.baidu.com/s/1mkb9sSnJMSx92Pw0enWCow)**, Password:df3d

The download link for the original Deep Fashshion3D:  
Google Drive: **[[Google Drive]](https://drive.google.com/drive/folders/1JWkrjoJk7ATBhtanNm6aUOhFswRYD1WP?usp=sharing)** 
Baiduyun Drive: **[[Baidu Drive]](https://pan.baidu.com/s/1MyPj02eMqSFOSlDRPc9ufg)**, Password:df3d

---

# Data Organization
### Deep Fashion3D V2
![plot](https://github.com/GAP-LAB-CUHK-SZ/deepFashion3D/assets/6134940/27e0d528-b38d-4973-ad63-c72576ac8edd)


#### Dense Point Cloud
The dense garment point cloud provided in Deep Fashion3D V2 follows the below structure, note that we coarsely aligned the garments with respect to a t-posed SMPL model. Therefore, the rotation and translation for Deep Fashion3D V2 may be slightly different from the original version.
```
deepFashion3DV2/point_cloud
|--- 1---1-1.ply # 1-1 indicates the first pose of garment #1
|    |---1-2.ply # high-resolution GT point cloud
|
|--- 2---2-1.ply
|    ....
|
|--- cloth_type_list.txt # clothes and types
```

#### Registered Garment Mesh
The **registered garment mesh** provided in Deep Fashion3D V2 follows the below structure. Note that we filtered the implausible registrations manually so that the number of registered garment meshes may not match the number of dense garment point clouds.

```
deepFashion3DV2/filtered_registered_mesh
|-- 1-1
|   |-- 1-1_tex.png  
|   |-- model_cleaned.obj 
|   |-- model_cleaned.obj.mtl
|
|-- 2-2
    |-- 2-2_tex.png  
    |-- model_cleaned.obj
    |-- model_cleaned.obj.mtl
    
```
For each successful registration, we provide **registered garment mesh** with **category-specific triangulation** and **high resolution(2048px x 2048px) textures**.

#### Garment Feature Line Annotation
The garment feature line annotation provided in Deep Fashion3D V2 follows the below structure. Note that we filtered the implausible annotations manually so that the number of annotations may not match the number of dense garment point clouds.
```
deepFashion3DV2/featureline_annotation
| --- 1 --- 1_1
|     |      |--- 1_1_1.ply # feature line annotations     
|     |      |--- 1_1_2.ply     
|     |      |--- ...   
|     |            
|     | --- 1_2
|
| --- 2
| --- ...
```
Different from the annotations in the original Deep Fashion3D, we only annotate the **"outermost" curves** of the garments as the feature line.  For the **upper-body clothing**, i.e., **long/short/no sleeve uppers**, and **long/short/no sleeve dresses**, Deep Fashion3D V2 contains following types of feature line annotations:
- 1 : Neck line
- 2 : Left cuff
- 3 : Right cuff
- 4 : Hemline

For **long/short pants**, Deep Fashion3D V2 contains following types of feature line annotations:
- 1 : Waist Line
- 2 : Left hemline of the trousers
- 3 : Right hemline of the trousers

For **long/short skirts**, Deep Fashion3D V2 contains following types of feature line annotations:
- 1 : Waist Line
- 2 : Hemline

#### Garment Pose Annotations
The garment pose annotations provided in Deep Fashion3D V2 follow the below structure. Each file contains the SMPL pose parameters, scale, and translation. 
```
deepFashion3DV2/pose_estimation
|-- 1
|   |-- 1_1.pkl
|   |-- 1_2.pkl
|-- 2
    |-- 2_1.pkl
```

---
### Deep Fashion3D 
The original Deep Fashion3D dataset follows the below structure:
```
deepFashion3D/deep_fashion_3d_point_cloud
|--- 1---1-1.ply # 1-1 indicates the first pose of garment #1
|    |---1-2.ply # high-resolution GT point cloud
|
|--- 2---2-1.ply
|    ....
|
|--- cloth_type_list.txt # clothes and types

deepFashion3D/deep_fashion_3d_point_cloud_annotations
| --- 1 --- 1-1
|     |      |--- 1-1-1.ply # feature line annotations        
|     |      |--- 1-1-2.ply    
|     |      |--- ...      
|     |            
|     | --- 1-2
|
| --- 2
| --- ...
```
Upper-body clothes in Deep Fashion3D contain following types of annotations:
- 1 : Neck line
- 2 : Left shoulder line
- 3 : Left elbow line
- 4 : Left wrist line
- 7 : Right shoulder line
- 8 : Right elbow line
- 9 : Right wrist line
- 10: Waist line
- 11: Hemline

Lower body clothes in Deep Fashion3D contain following types of annotations
- 1 : Waist Line
- 2 : Left Knee
- 3 : Left Ankle
- 4 : Right Knee
- 5 : Right Ankle
- 6 : Hemline 

<br>

---

# Citation
If you use Deep Fashion3D or Deep Fashion3D V2 in your work, please consider citing our paper! 
``` 
@misc{zhu2020deep,
    title={Deep Fashion3D: A Dataset and Benchmark for 3D Garment Reconstruction from Single Images},
    author={Heming Zhu and Yu Cao and Hang Jin and Weikai Chen and Dong Du and Zhangye Wang and Shuguang Cui and Xiaoguang Han},
    year={2020},
    eprint={2003.12753},
    archivePrefix={arXiv},
    primaryClass={cs.CV}
}

```
