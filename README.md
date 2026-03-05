OrnithoAI Pro v2.0

Dual-Stage Browser-Based Bird Detection & Species Classification

OrnithoAI Pro is a fully client-side bird detection and classification system built with TensorFlow.js. It combines object detection (COCO-SSD) and image classification (MobileNetV2) into a two-stage pipeline for more precise bird identification directly in the browser.

No server uploads. No cloud processing. All inference runs locally using WebGL acceleration.

⸻

Overview

Unlike single-stage image classifiers, OrnithoAI Pro first detects birds in an image using object detection, then classifies the detected region using a separate species classification model.

Pipeline:
	1.	Detect birds using COCO-SSD
	2.	Extract region of interest (ROI)
	3.	Classify using MobileNetV2
	4.	Aggregate confidence scores
	5.	Display species information and metadata

⸻

Key Features
	•	Dual-Stage AI Pipeline (Detection + Classification)
	•	100% Client-Side Inference (Privacy-Preserving)
	•	WebGL GPU Acceleration
	•	Live Camera Detection (Real-Time)
	•	Drag-and-Drop Image Upload
	•	URL Image Analysis (CORS compliant)
	•	JSON Export Reports
	•	Detection History Tracking
	•	Responsive UI (Desktop + Mobile)

⸻

Technology Stack

Machine Learning
	•	TensorFlow.js v4.x
	•	COCO-SSD (MobileNet v2 backbone)
	•	MobileNetV2 (ImageNet pretrained)

Frontend
	•	HTML5
	•	Tailwind CSS
	•	Chart.js
	•	Canvas API
	•	MediaDevices API

Execution Backend
	•	WebGL (Primary)
	•	CPU fallback (Automatic)

⸻

AI Architecture

Stage 1 — Object Detection (COCO-SSD)

Input: Raw image
Output: Bounding boxes + class probabilities

Process:
	•	Image preprocessing
	•	SSD inference
	•	Filter predictions where class == “bird”
	•	Apply confidence threshold
	•	Render bounding boxes

Average inference time:
50–100 ms (GPU)

⸻

Stage 2 — Species Classification (MobileNetV2)

Input: Cropped bird region (224×224)
Output: Top-K predictions

Process:
	•	Crop ROI
	•	Normalize (pixel / 255)
	•	Feature extraction
	•	Top-5 predictions
	•	Species database mapping

Average inference time:
30–60 ms (GPU)

⸻

Ensemble Confidence

Final score is computed by combining:

Detection Confidence × Classification Confidence

Confidence Levels:
	•	High: > 0.80
	•	Medium: 0.50 – 0.80
	•	Low: < 0.50

⸻

Installation

Option 1 — Direct Use (Recommended)
	1.	Download the HTML file
	2.	Open in a modern browser
	3.	No setup required
Usage

Upload Image
	•	Drag and drop image (JPG, PNG, WEBP)
	•	Max size: 10MB
	•	View bounding boxes and classification panel

Live Camera
	•	Grant camera permission
	•	Start detection
	•	Real-time bounding boxes rendered at ~25–30 FPS

Image URL
	•	Paste direct image URL
	•	Must allow CORS
	•	Click Analyze

⸻

Species Database

Built-in species mapping includes:
	•	Peacock (Pavo cristatus)
	•	Eagle (Accipitridae)
	•	Owl (Strigiformes)
	•	Penguin (Spheniscidae)
	•	Flamingo (Phoenicopterus)
	•	Toucan (Ramphastidae)
	•	Parrot (Psittaciformes)
	•	Sparrow (Passeridae)
	•	Heron (Ardeidae)

Each species entry contains:
	•	Scientific name
	•	Habitat
	•	Diet
	•	Visual features (beak, plumage, posture)
	•	Base confidence weight
