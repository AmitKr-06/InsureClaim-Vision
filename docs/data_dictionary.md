# CarDD Dataset — Data Dictionary and License Record

## Source
- **Dataset name:** CarDD (Car Damage Detection)
- **Original URL:** https://cardd-ustc.github.io/
- **Kaggle mirror used:** https://www.kaggle.com/datasets/asfarhossainsitab/car-damage-detection
- **Citation:** Wang, Y., Li, Y., & Wu, J. (2023). CarDD: A New Dataset for Vision-based Car Damage Detection. *IEEE Transactions on Intelligent Transportation Systems*.
- **Task:** Object detection (bounding boxes) + instance segmentation masks.

## License
- **Original license:** CarDD requires prior consent from PIC Lab (USTC). Commercial use requires separate authorization.
- **This project's use:** Research and portfolio demonstration only. No commercial deployment intended. The Kaggle mirror is used for convenience; original terms apply.
- **Redistribution:** The `data/processed/cardd_yolo/` outputs are derived from CarDD. Do not redistribute without re-verifying CarDD's terms.

## Splits
| Split | Images | Total instances |
|---|---|---|
| Train | 2816 | 6211 |
| Val | 810 | 1744 |
| Test | 374 | 785 |

## Classes (6 damage types)
| YOLO ID | COCO ID | Name | Train count | Test count |
|---|---|---|---|---|
| 0 | 1 | dent | 1806 | 236 |
| 1 | 2 | scratch | 2560 | 307 |
| 2 | 3 | crack | 651 | 70 |
| 3 | 4 | glass shatter | 475 | 71 |
| 4 | 5 | lamp broken | 494 | 69 |
| 5 | 6 | tire flat | 225 | 32 |

## Notes
- Class imbalance: scratch is ~11x more frequent than tire flat. Expect weaker per-class performance on tire flat.
- COCO `area` field is **mask area**, not box area. See `reports/metrics/cardd_instances.csv` for both.
- No whole (undamaged) images in CarDD. The detector must be validated on separate whole-car images (see Notebook 05 test set).
