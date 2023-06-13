# Object Detection Demo

This is a simple object detection application that performs real-time object detection using TensorFlow.js and the COCO-SSD model. It allows you to collect images of specific objects from your webcam and store them for later use.

## Prerequisites

Before running the demo, make sure you have the following prerequisites installed:

### Node.js & npm

Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine, and npm is the package manager for Node.js. Both are essential for this project.

- You can download and install Node.js and npm from the official Node.js website at [https://nodejs.org/](https://nodejs.org/). The npm is included in the Node.js distribution.
- To verify that you have installed Node.js and npm correctly, you can use the following commands:

```bash
node -v
npm -v
```

These will display the version of Node.js and npm installed on your system, respectively.

### http-server

This is a simple, zero-configuration command-line HTTP server for Node.js. It is needed to serve your project files.

- After you have installed Node.js and npm, you can install http-server globally on your computer by running the following command:

```bash
npm install --global http-server
```

- To verify that you have installed http-server correctly, you can use the following command:

```bash
http-server -v
```

- This will display the version of http-server installed on your system.

### Web Browser

A modern web browser (like Google Chrome, Mozilla Firefox, Apple Safari, or Microsoft Edge) is required to open and run the object detection application.

- The browser must be compatible with TensorFlow.js. You can check the compatibility list here: [https://js.tensorflow.org/debug](https://js.tensorflow.org/debug).
- The browser must also support WebRTC for accessing the webcam. Most modern web browsers do support this. You can check your browser's compatibility with WebRTC here: [https://webrtc.github.io/samples/](https://webrtc.github.io/samples/).

### Webcam To capture images for object detection, you'll need a webcam connected to your computer. The demo will ask for permission to access your webcam.

Please note, all these instructions are for the setup on a local machine. If you are using a virtual machine, a server, or a container, the steps may vary.

## Setup

1. Clone this repository:

```bash
    Copy code git clone <repository-url>
```

2. Navigate to the project directory:

```bash
Copy code cd object-detection-demo
```

3. Install the dependencies:

```bash
 npm install
```

## Usage

To start the object detection demo, run the following command:

```bash
http-server
```

This will launch the application and open it in your default web browser. You can then use the webcam to perform real-time object detection and collect images of specific objects.

### Selecting Objects to Collect

You can select the type of objects you want to collect by choosing from the dropdown menu on the main page. The available options will be populated based on the COCO-SSD model's predefined object classes.

### Storing Collected Images

When you click the "Start Collecting Images" button, the application will start detecting objects in the video stream. If an object of the selected type is detected, an image will be captured and stored in the IndexedDB database.

### Viewing Stored Images

You can view the stored images by clicking the "Show Stored Images" button. This will open a modal that displays the collected images. You can navigate through the images using the pagination controls.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvement, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License.

## Code

The project includes three main files: `index.html`, `styles.css`, and `script.js`.

The JavaScript file uses TensorFlow.js to interact with the COCO-SSD object detection model. It sets up a webcam feed and starts collecting images of the selected object type when the "Start Collecting Images" button is clicked. Collected images are stored in IndexedDB. You can view the stored images by clicking the "Show Stored Images" button.

## Note

Remember to serve these files from a server, as the Fetch API used by TensorFlow.js does not work with the `file://` protocol due to security restrictions in browsers. You can use a simple server like `http-server` in Node.js for this purpose.