
# Deep Human Action Recognition With ResNet50 as Entry Flow Network

## Overview

This repository is a fork of the original project by D. Luvizon, D. Picard, and H. Tabia, focusing on multi-task deep learning for real-time 3D human pose estimation and action recognition. Significant enhancements have been made to incorporate ResNet50 as the entry flow network, improving feature extraction capabilities. Additionally, a Jupyter notebook has been added for easy execution in Google Colab.

### Key Updates

- **Entry Flow Network:** Integrated ResNet50 as the entry flow network to enhance feature extraction.
- **Jupyter Notebook:** Provided a Jupyter notebook designed for seamless execution in Google Colab. [Deephar Resnet](Daniel_Resnet_Deephar.ipynb)
- **TensorFlow and Keras Compatibility:** Updated codebase for compatibility with the latest TensorFlow and Keras versions.
- **Requirements.txt:** Adjusted the `requirements.txt` file to include new libraries necessary for the updated model.

### Changes in Detail


1. **TensorFlow Installation:** Changed from `tensorflow-gpu==1.6.0` to `tensorflow[and-cuda]`.
2. **Keras Functions:** In [Annotation helper](datasets/annothelper.py), updated the import statement from `from keras.utils.data_utils import get_file` to `from tensorflow.keras.utils import get_file`, as Keras 2.15.0 is now bundled with TensorFlow.
3. **Data Types:** In `penn_tool`, updated `np.float` to `np.float64` for better precision and compatibility.
4. **Error Handling:** Modified line 69 in `pen tools` from:
   ```python
   # correct = np.equal(np.argmax(y_true, axis=-1), np.argmax(y_pred[:, b, :], axis=-1), dtype=np.float)
   ```
   to:
   ```python
   correct = np.equal(np.argmax(y_true, axis=-1), np.argmax(y_pred[:, b, :], axis=-1))
   ```
5. **Optimizer:** Switched to legacy optimizer `RMSprop`.

### Multi-task Model for 2D Pose Estimation and Action Recognition

The multi-task model can now be evaluated on MPII for pose estimation and on PennAction for action recognition with the enhanced feature extraction capabilities provided by ResNet50.

### Credits

Original work credits:
```
@ARTICLE{Luvizon_2020_TPAMI,
  author={D. {Luvizon} and D. {Picard} and H. {Tabia}},
  journal={IEEE Transactions on Pattern Analysis and Machine Intelligence}, 
  title={Multi-task Deep Learning for Real-Time 3D Human Pose Estimation and Action Recognition}, 
  year={2020},
  volume={},
  number={},
  pages={1-1},
}

@InProceedings{Luvizon_2018_CVPR,
  author = {Luvizon, Diogo C. and Picard, David and Tabia, Hedi},
  title = {2D/3D Pose Estimation and Action Recognition Using Multitask Deep Learning},
  booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  month = {June},
  year = {2018}
}
```

## License

MIT License

---

This updated README reflects the enhancements and modifications you've made to the original repository, providing a clear overview of the changes and their impact on the project.
