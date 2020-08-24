# News
**2020-8-24** Deep Fashion3D is released with garment models. Feature line annotations and garment pose annotations will be released soon.
<br>

# Download
Please fill [the form](https://forms.gle/1SMrPHCyS3m7pkXM6) to get password for unzipping the compressed file.

Google Drive: [[Google Drive]](https://twitter.com/home), to be uploaded  
Baiduyun Drive: [[Baidu Drive]](https://pan.baidu.com/s/1MyPj02eMqSFOSlDRPc9ufg), Password:df3d

<br>

# Data Organization
Deep Fashion3D dataset follows the below structure:
```
deepFashion3D/deep_fashion_3d_point_cloud
|--- 1---1-1.ply # 1-1 indicates the first pose of garment #1
|    |---1-2.ply # high resolution GT point cloud
|
|--- 2---2-1.ply
|    ....
|
|--- cloth_type_list.txt # clothes and types

deepFashion3D/deep_fashion_3d_point_cloud_nnnotations
| --- 1 --- 1-1---1-1.dat # garment pose parameters
|     |       |--- feature lines         
|     |            |--- 1-1-1.ply # feature line annotations
|     |            |--- 1-1-2.ply
|     |            |--- ...
|     | --- 1-2
|
| --- 2
| --- ...
```
Upper body clothes in Deep Fashion3D contains following types of annotations:
- 1 : Neck line
- 2 : Left shoulder line
- 3 : Left elbow line
- 4 : Left wrist line
- 7 : Right shoulder line
- 8 : Right elbow line
- 9 : Right wrist line
- 10: Waist line
- 11: Hemline

Lower body clothes in Deep Fashion3D contains following types of annotations
- 1 : Waist Line
- 2 : Left Knee
- 3 : Left Ankle
- 4 : Right Knee
- 5 : Right Ankle
- 6 : Hemline 


<br>

# Citation
If you use Deep Fashion3D in your work, please consider citing our paper! 
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
