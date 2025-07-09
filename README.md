# Player-reidentification
This project aims to identify and track football players across two different video feeds — a **tactical cam** (wide-field view) and a **broadcast cam** (dynamic close-up view). The system ensures each player is assigned a **consistent ID** across both views using visual appearance and AI models.

---

## ✅ Key Features

- 🧠 **Player Detection** using a custom YOLOv11 model
- 🧬 **Appearance Matching** using OpenAI’s CLIP model
- 🔁 **Consistent ID Assignment** across both videos
- 📝 **CSV Output** with frame-wise player locations and IDs
- 🎥 **Video Output** with bounding boxes and consistent IDs

---

## 📂 Input Files

| File Name        | Description                             |
|------------------|-----------------------------------------|
| `best.pt`        | YOLOv11 model trained to detect players |
| `tacticam.mp4`   | Wide-angle tactical view video          |
| `broadcast.mp4`  | Broadcast-style game footage            |

---

## ⚙️ How It Works

1. **Detect players** in each frame using YOLO (`best.pt`)
2. **Extract visual features** for each player using CLIP (`ViT-B/32`)
3. **Match players** between views using cosine similarity + Hungarian algorithm
4. **Assign consistent player IDs** across views
5. **Write results** to a video and a CSV file

---

## 📤 Output Files

| File Name            | Description                                     |
|----------------------|-------------------------------------------------|
| `matched_output.mp4` | Side-by-side video with consistent player IDs   |
| `player_tracking.csv`| Player ID, frame number, view, and bounding box |

#### Example: `player_tracking.csv`
