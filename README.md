# 🎨 Interactive HSV Color Tuner

A real-time HSV color range tuner built with Python and OpenCV. Use interactive sliders to find the perfect HSV threshold values for any color segmentation task — great for preprocessing pipelines in computer vision projects.

---

## ✨ Features

- 🎛️ **6 live sliders** — independently control H, S, V min/max values in real time
- 🖼️ **Side-by-side preview** — original image and masked result displayed together
- 🔵 **Morphological cleanup** — auto applies CLOSE and OPEN operations to reduce noise in the mask
- ⚡ **Instant feedback** — every slider change updates the mask immediately

---

## 🛠️ Requirements

- Python 3.8+
- OpenCV (`opencv-python`)
- NumPy

Install dependencies:

```bash
pip install opencv-python numpy
```

---

## 🚀 Usage

1. Place your image in the project directory and set the path in the script:

```python
image_path = "your_image.png"
```

2. Run the script:

```bash
python hsv_tuner.py
```

3. Use the sliders in the **HSV Tuner** window to adjust the color range.
4. Press **`ESC`** to exit.

---

## 🧠 How It Works

| Step | Description |
|------|-------------|
| **Load image** | Reads the input image with OpenCV |
| **Convert to HSV** | Transforms the color space from BGR to HSV for easier color filtering |
| **Trackbar UI** | 6 sliders let you interactively set H/S/V min & max thresholds |
| **Mask generation** | `cv2.inRange()` creates a binary mask based on current slider values |
| **Morphology** | CLOSE (fills gaps) then OPEN (removes noise) clean up the mask |
| **Preview** | Original and masked result shown side-by-side at 450×400 each |

---

## 🎯 Use Case Example

This tool is ideal for isolating specific colored objects — for example, segmenting a **tomato** from its background by tuning the red/orange HSV range. Once you find the right values, you can copy them directly into your main computer vision pipeline.

---

## 📁 Project Structure

```
├── hsv_tuner.py       # Main script
├── tomato.png         # Sample input image
└── README.md
```

---

## 📌 Notes

- HSV color space separates color (Hue) from brightness (Value), making it more robust to lighting changes than BGR/RGB.
- For **red colors**, note that red wraps around in HSV (0–10 and 170–179). You may need to combine two masks with `cv2.bitwise_or()`.
- Slider defaults are pre-set for green/yellow tones — adjust them for your target color.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
