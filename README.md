# Prototype — Eco Watch

A browser-based live camera prototype for object detection and possible e-waste alerts.

## Run it
1. Open the site over HTTPS (GitHub Pages works) or use localhost.
2. Press **Start live scan** and allow camera access.
3. Keep the camera pointed at objects in good lighting. Press **Stop** to end the camera session.

## What it does
- Uses TensorFlow.js and the COCO-SSD Lite MobileNet model in the browser.
- Continuously detects common COCO objects from the webcam.
- Marks phones, laptops, keyboards, mice, TVs and remote controls as **possible e-waste candidates** and uses a distinct visual/audio/browser notification alert for those detections.
- Logs other recognized objects without the e-waste alert.

## Important limitations
This is **not** a custom-trained waste detector. The underlying COCO-SSD model recognizes common object categories, not whether an item is actually waste. It does not recognize every waste type and can miss e-waste such as loose circuit boards, cables, batteries, chargers, and small components. Alerts need human verification. For a dependable all-waste system, replace the generic model with a properly trained and evaluated waste-classification/detection model.

Camera frames are processed in the browser and are not uploaded by this code. The TensorFlow.js library and model are fetched from public CDNs, so an internet connection is needed to load the model.
