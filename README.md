ABLDataset is a specialized dataset designed for the detection and localization of active blue emergency lights in road scenarios, created from publicly available YouTube videos. This dataset aims to provide a high-quality resource to facilitate research in real-time detection of emergency vehicles using computer vision and deep learning methodologies.

## Dataset Contents

The repository is structured as follows:

```
ABLDataset/
├── labels/
│   ├── train/
│   ├── val/
│   ├── test/
│   └── test_id/
├── videos.json
└── info_videos.txt
```

- `labels/train`, `labels/val`, and `labels/test`: Contain YOLO-format annotations of frames extracted from the videos. These annotations highlight active blue emergency lights.

- `labels/test_id`: Contains annotations identifying individual vehicles in the test set, allowing detailed evaluation at the vehicle level.

- `videos.json`: Contains metadata about each video used, including:
  - Dataset title of the video.
  - URL to the original YouTube video.
  - Specific annotated frames.

- `info_videos.txt`: Contains the dataset title, URL of the video, and the original YouTube title.

## Annotation Format

Annotations are provided in the YOLO format:

```
<class> <x_center> <y_center> <width> <height>
```

- `class`: Currently a single class (0), corresponding to active blue lights.
- `(x_center, y_center)`: Normalized coordinates of the bounding box center.

## Dataset Distribution

- **Train:** 2112 images, 7208 annotations
- **Validation:** 482 images, 1586 annotations
- **Test:** 455 images, 1643 annotations

## Bounding Box Statistics

To characterize the apparent size of the active blue lights in the dataset, the bounding-box annotations of the training split were analyzed. The training split contains 7,207 annotated light instances and was used as a representative sample of the complete dataset. Assuming the Full HD (1920$\times$1080) image resolution, the following statistics were obtained:

| Metric      |    Mean | Standard deviation | Median | Minimum |   Maximum |
| ----------- | ------: | -----------------: | -----: | ------: | --------: |
| Width (px)  |    42.2 |               47.4 |      — |     2.0 |     802.5 |
| Height (px) |    23.4 |               22.3 |      — |     3.0 |     361.5 |
| Area (px²)  | 1,790.2 |            6,236.4 |  462.0 |     8.0 | 197,415.3 |

The distribution of the bounding-box area is right-skewed due to the wide range of distances at which active blue lights appear in the images. Most annotations correspond to relatively small light regions, while closer instances result in substantially larger bounding boxes.

## Related Research

This dataset was specifically created and utilized in the research described in:

> Vacalebri-Lloret, F., Banchero, L., Lopez, J. J., & Mossi, José M. (2025). "A 360° Multi-camera System for Blue Emergency Light Detection Using Color Attention RT-DETR and the ABLDataset." *IEEE Transactions on Intelligent Transportation Systems.*

## Application

ABLDataset supports training and evaluation of models aimed at enhancing Advanced Driver Assistance Systems (ADAS), particularly in scenarios requiring precise and early detection of emergency vehicles based on active blue lights.

## License and Usage

The ABLDataset is provided for academic and non-commercial research purposes. Please cite our publication when using this dataset.

## Citation

If you use this dataset in your research, please cite:

```
@article{Vacalebri2025ABLDataset,
  title={A 360° Multi-camera System for Blue Emergency Light Detection Using Color Attention RT-DETR and the ABLDataset},
  author={Vacalebri-Lloret, Francisco and Banchero, Lucas and Lopez, Jose J. and Mossi, José M.},
  journal={IEEE Transactions on Intelligent Transportation Systems},
  year={2025}
}
```

## Acknowledgements

- [Juan Emergencias](https://www.youtube.com/@juanemergencias)
- [Urgences Genève](https://www.youtube.com/@UrgencesGeneve)

