The public database is available at the following URL:
https://dmsgrdm.riken.jp:5000/wbpyk/

This repository contains the facial expression database described in the following paper:

- Development of a Facial Expression Database Covering Diverse Emotional States Using Large Language Models and an Android Robot

## Metadata

`database/summary.csv` contains following information.


* **`img_id`**: Unique image ID in the format `{emotion_label_id}_{image_number}`(each zero-padded to three digits).

* **`emotion_label_id`**: ID of the emotion label, ranging from 1 to 75.

* **`emotion_label_name`**: English name of the emotion label.

* **`image_filename`**: Path to the image relative to the `database/` directory.

* **`category`**: The possible values are:

  * final_database
  * excluded/second_phase
  * excluded/third_phase

* **`second_phase_appropriate_percent`**: Percentage of online evaluators in the second-phase evaluation who judged the image appropriate for the presented emotion label.

* **`third_phase_appropriate_percent`**: Percentage of the in-person evaluators in the third-phase evaluation who judged the expression appropriate for the presented emotion label. This field is empty for images excluded during the second-phase evaluation.


## Repository Structure

```text
.
├── database/
│   ├── summary.csv
│   ├── final_database/
│   │   ├── 001/           # emotion_label_id
│   │   │   ├── 001.jpg    # image_number
│   │   │   ├── 002.jpg
│   │   │   └── ...
│   │   ├── 002/
│   │   ├── ...
│   │   └── 075/
│   └── excluded/
│       ├── second_phase/
│       │   ├── 002/
│       │   │   ├── 001.jpg
│       │   │   └── ...
│       │   └── ...
│       └── third_phase/
│           ├── 003/
│           │   ├── 005.jpg
│           │   └── ...
│           └── ...
│
└── analysis_codes/
    ├── fig3_01_llm_analysis.ipynb
    ├── fig3_02_visualization.ipynb
    ├── fig4_01_pyfeat_analysis.ipynb
    ├── fig4_02_visualization.ipynb
    ├── fig5_01_llm_analysis.ipynb
    ├── fig5_02_visualization.ipynb
    ├── data/
    │   ├── labels_en.txt
    │   └── labels_jp.txt
    ├── results/
    │   ├── fig3_cluster_results_paper.csv
    │   ├── fig3_labels_va_results_paper.csv
    │   ├── fig4_photos_pyfeat_paper.csv
    │   └── fig5_photos_va_results_paper.csv
    └── results_fig/
        ├── fig3_paper.png
        ├── fig4_paper_c1.png
        ├── fig4_paper_c2.png
        ├── fig4_paper_c3.png
        ├── fig4_paper_c4.png
        ├── fig4_paper_c5.png
        └── fig5_paper.png
```
