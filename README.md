# 🎥 AI-Powered Sports Highlights Generator (Volleyball – Visual Only)

This project automatically generates highlight videos from long sports recordings using computer vision and AI.  
The current version focuses on **volleyball matches** and extracts the most “exciting” moments based on visual cues such as player celebrations, crowd reactions, motion intensity, and scene changes.

The system is designed to be simple to run in **Google Colab** and scalable to longer videos.

---

## 🚀 Features

- Automatic highlight extraction from full-length match videos  
- Visual understanding using CLIP (vision–language model)  
- Motion-based excitement detection  
- Scene change detection for broadcast-style dynamics  
- Two-pass scoring for efficiency on large videos  
- Generates a final stitched highlight video (`highlights.mp4`)  

---

## 🧠 How It Works

1. **Video Segmentation**  
   The input video is split into short segments (e.g. 5 seconds) using ffmpeg.

2. **Visual Feature Extraction**  
   For each segment:
   - Sample a few frames  
   - Compute:
     - Semantic similarity to “exciting” volleyball concepts (using CLIP)  
     - Motion intensity between frames  
     - Scene change frequency  

3. **Highlight Scoring**  
   A weighted combination of:
   - CLIP semantic score (celebrations, cheering, high-fives)  
   - Motion score  
   - Scene change score  

4. **Highlight Selection**  
   The top-K most exciting segments are selected.

5. **Video Stitching**  
   Selected segments are concatenated into a final highlight video.

---

## 🛠️ Technologies Used

- **Python**  
- **Google Colab**  
- **ffmpeg**  
- **OpenCV (cv2)**  
- **PyTorch**  
- **CLIP (OpenAI)**  
- **NumPy**  
- **Matplotlib**  
- **Pillow (PIL)**  

---

## 📦 Setup & Usage (Summary)

1. Mount Google Drive in Colab  
2. Set `VIDEO_PATH` to your input video  
3. Segment the video with ffmpeg  
4. Run the highlight extraction pipeline  
5. Download `highlights.mp4`

(See the notebook for full step-by-step instructions.)

---

## 🔮 Future Work / Improvements

- Add **audio-based excitement detection** (crowd cheering, whistles, commentator hype)  
- Use **speech recognition** for semantic cues from commentary  
- Train a dedicated **highlight detection model** on labeled sports datasets  
- Add **player detection / pose estimation** for better action understanding  
- Generate **vertical highlights** for social media (TikTok/Reels)  
- Add **context before and after** each highlight segment  
- Extend to **multiple sports** (football, basketball, tennis, etc.)  
- Build a simple **web app** for user uploads  

---

## 📌 Disclaimer

This is a prototype. Performance depends on video quality, camera angles, and broadcast style.

---

## 🙌 Motivation

This project explores **multimodal AI for video understanding** and automated content creation, combining foundation models (CLIP) with classic computer vision techniques to extract meaningful highlights from sports videos.
