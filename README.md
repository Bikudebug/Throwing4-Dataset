z# **Throwing4: Phase-Aware Pose Modeling for Throw-Distance Prediction in Elite Athletics**

![Throwing4 Phase Examples](figures/throwing4_phases.png)
🏟️ **Throwing4** is a multi-modal benchmark dataset created for vision-based analysis of elite athletics throwing actions. The dataset contains **500 valid throwing clips** from four Olympic throwing events, along with RGB videos, action annotations, frame-wise 2D skeleton data, biomechanical phase labels, and official throw-distance values.

The dataset covers four throwing categories:

**1) Javelin Throw**

**2) Discus Throw**

**3) Hammer Throw**

**4) Shot Put**

Throwing4 is designed for tasks such as throw-distance prediction, phase-aware pose modeling, skeleton-based action analysis, temporal phase localization, and sports performance understanding from broadcast videos.

---

## **🗃️ Dataset Features**

**Total Clips:** 500

**Throwing Classes:** 4

- Javelin Throw
- Discus Throw
- Hammer Throw
- Shot Put

**Annotations:**

- Action annotation files
- Frame-level phase boundaries
- Official throw-distance labels
- Valid elite non-foul throwing attempts

**Pose/Skeleton Data:**

- Frame-wise 2D human pose keypoints
- Identity-consistent thrower tracking
- MPII-16 skeleton format
- Main athlete selected and tracked across frames

**Phase Labels:**

- Javelin Throw: Step, Drive, Throw, Recovery
- Discus Throw: Swing, Turn, Throw, Recovery
- Hammer Throw: Swing, Turn, Throw, Recovery
- Shot Put: Stance, Glide, Throw, Recovery

---

## **📊 Dataset Statistics**

| Sport | Clips | Male/Female | Phase Sequence |
|---|---:|---:|---|
| Javelin Throw | 211 | 111 / 100 | Step → Drive → Throw → Recovery |
| Discus Throw | 112 | 69 / 43 | Swing → Turn → Throw → Recovery |
| Hammer Throw | 90 | 30 / 60 | Swing → Turn → Throw → Recovery |
| Shot Put | 87 | 55 / 32 | Stance → Glide → Throw → Recovery |
| **Total** | **500** | — | — |

---

## **📂 Dataset Structure**

```bash
THrowing4_Dataset/
├── javelin throw/
│   ├── Action annotaion/
│   │   ├── video_0.json
│   │   └── ...
│   ├── RGB_Videos/
│   │   ├── video_0.mp4
│   │   └── ...
│   └── Skeleton _data/
│       ├── Video_0.json
│       └── ...
├── Discus Throw/
│   ├── Action annotaion/
│   ├── RGB_Videos/
│   └── Skeleton _data/
├── Hammer Throow/
│   ├── Action annotaion/
│   ├── RGB_Videos/
│   └── Skeleton _data/
└── Shot put/
    ├── Action annotaion/
    ├── RGB_Videos/
    └── Skeleton _data/
```

The dataset is organized sport-wise. Each sport folder contains:

- **`Action annotaion/`**: JSON annotation files containing action information, phase boundaries, and throw-distance labels
- **`RGB_Videos/`**: RGB clips of complete throwing attempts
- **`Skeleton _data/`**: JSON files containing frame-wise 2D skeleton keypoints

---

## **Pose Estimation**

The pose estimations from RGB videos are extracted using the [**MMPose**](https://github.com/open-mmlab/mmpose) framework. The extracted skeletons follow the **MPII-16** 2D pose format.

The pipeline contains:

- RGB video input
- Person detection
- Main thrower selection
- Identity-consistent thrower tracking
- Frame-wise 2D skeleton extraction


---

## **Skeleton Data Format**

Each skeleton file stores the 2D pose sequence of the main throwing athlete:

```text
T × J × C
```

where:

- **T** = number of frames
- **J = 16** = MPII body joints
- **C** = coordinate channels, usually `(x, y)` or `(x, y, confidence)`


---

## **Dataset Access**

We will provide a public link to access this dataset after publication.

📥 **[Download Dataset (Available after publication)](https://drive.google.com/drive/folders/1gGA55OZtFihCrIE38qJ29wWStexGfVdC?usp=drive_link)**

---

## **Citation**

If you use Throwing4 in your research, please cite:

```bibtex
@article{badatya2026throwing4,
  title={Throwing4: Phase-Aware Pose Modeling for Throw-Distance Prediction in Elite Athletics},
  author={Badatya, Bikash Kumar and Tiwari, Kartike and Amin, Jyotirmoy and Hegde, Ravi},
  year={2026}
}
```



