# Website project copy

**Title:** Machine Learning for Voice Pathology Classification

**Short card text:** Exploring voice-disorder classification using electroglottography and neck-surface recordings, handcrafted acoustic features, and feature-level multimodal fusion.

**Tech tags:** Python · Librosa · scikit-learn · Biomedical Signal Processing · Random Forest · GroupKFold

## Case study

This academic project investigated the ability of machine-learning models to distinguish healthy voice recordings from laryngitis, hyperfunctional dysphonia, and recurrent laryngeal nerve paralysis. I built preprocessing pipelines for EGG and NSP recordings, extracted acoustic and spectral features, and benchmarked four traditional classifiers. After exploring patient-wise feature selection and independent modalities, I combined complementary EGG and NSP features at patient level and obtained the project's best reported test accuracy: **50.35% with Random Forest**, compared with approximately 44% for the best single-modality models. I also prototyped a local microphone-based NSP classifier to investigate accessibility considerations.

**What this demonstrates:** Signal processing, feature engineering, model evaluation, data fusion, scientific interpretation and awareness of clinical validity limits.

**Limitations:** The prototype is an educational experiment—not a clinically validated voice-pathology detector. The original microphone demo requires a local model and audio hardware and cannot run directly in a static GitHub Pages site.

**Recommended imagery:** Use the real saved confusion-matrix images from `figures/`, especially `egg-nsp-fusion-normalized-confusion.png`.
