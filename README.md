# Shape-Aware Human Pose and Shape Reconstruction Using Multi-View Images

Based on the project ([Project Page](https://gamma.umd.edu/researchdirections/virtualtryon/humanmultiview))

### Requirements
- Python 2.7
- [TensorFlow](https://www.tensorflow.org/) tested on version 1.3

Run prepaired docker container
```
docker run -it --runtime=nvidia -e NVIDIA_VISIBLE_DEVICES=0 \ 
-p 2021:8888 --name human_reconstruction \
-v {data}:/data \ 
-v {code}:/code \
fitlab/human_reconstruction:latest bash
```

### Inference
1. Download the [pre-trained models](https://drive.google.com/file/d/1grEX6HmqL6CKittCyl_N6nggqIRIEOCt/view?usp=sharing)
2. Prepare images by passing them through openpose: 
*images should be cropped so that the height of the person is roughly 2/3 of the image height*
3. Run the demo:
```
 python -m demo --img_paths /data/demo_imgs/good_poses.csv --load_path models/model.ckpt-55124 --out_dir /data/demo_imgs/avatars 
```



### Training and Data

Please see doc/train.md.

### Citation
If you use this code for your research, please consider citing:
```
@inProceedings{liang2019shape,
  title={Shape-Aware Human Pose and Shape Reconstruction Using Multi-View Images},
  author = {Junbang Liang
  and Ming C. Lin},
  booktitle={International Conference on Computer Vision (ICCV)},
  year={2019}
}
```

### Acknowledgement
This project is derived from [HMR](https://github.com/akanazawa/hmr). If you have any question, feel free to refer to the original help doc or email liangjb@cs.umd.edu. This work is supported by National Science Foundation and Elizabeth S. Iribe Professorship.
