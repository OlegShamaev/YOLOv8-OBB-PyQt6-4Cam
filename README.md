# Advanced Video Processing Application
_______________________________________
- Author: `Oleg Shamaev`
- email `MlOpsEngineer@yandex.ru`
- GUI Framework: `PyQt6`
- Processing `Framework: Ultralytics`
_______________________________________

### Description in Russian [docs/docs/rus.md](docs/docs/rus.md)
### Installation and Configuration Guide [docs/docs/getting-started.md](docs/docs/getting-started.md)
_______________________________________

## DESCRIPTION:

- This is a powerful and flexible application developed using PyQt6, designed for real-time processing of 4 video streams using the YOLOv8-OBB model.

- The application renders detection results directly onto the original video stream, ensuring that even on low-end systems, the video stream remains smooth and free of stuttering. This approach minimizes the processing overhead typically associated with real-time video analysis, allowing for efficient performance without compromising the fluidity of the video. By optimizing the rendering process, the application delivers a seamless viewing experience, maintaining consistent frame rates even under limited hardware resources.

- You can select a detection area and choose to detect either inside or outside of it, effectively excluding certain regions from detection. This can be managed through the `Display Area` menu with the `IN` and `OUT` options.

- The application supports video processing from cameras and video files providing highly efficient object detection and result saving.

- It is aimed at users who require accurate and fast video data processing for analytics and monitoring.

    - Interface Structure:
        - `All Cameras`: Tab for displaying all cameras simultaneously. Allows monitoring all video streams in one window.

        <img src="docs/docs/images/all.jpg" alt="Project Logo" width="600">

        - `Camera` 1-4: Individual tabs for each camera.

         <img src="docs/docs/images/area.png" alt="Project Logo" width="600">

        - `Settings`: Video stream settings tab. Allows configuring detection, recording, and interface parameters.

        <img src="docs/docs/images/settings.png" alt="Project Logo" width="600">


- Key Features:

    - Multi-Camera Processing:
        - The application provides 6 tabs.
        - The first tab displays all cameras simultaneously (`All Camera`)
            - AiWorkers:
                - [x] Cam1 AllCamera
                - [x] Cam2 AllCamera
                - [x] Cam3 AllCamera
                - [x] Cam4 AllCamera

        - The next four tabs are designed for working with each camera individually.        
        - The last tab is used for parameter `settings`.
            - Supported Input Sources:
                - [x] local files: images or videos
                - [x] Camera
                - [x] RTSP-Stream

            - Supported Models:
                - [x] YOLOv8n
                - [x] YOLOv8s
                - [x] YOLOv8m
                - [x] YOLOv8l
                - [x] YOLOv8x

            - Display Area:
                - [x] IN
                - [x] OUT

    - Load Optimization:
        - Video processing is only performed on the active tab, reducing system load.
        - On the` All Cameras` tab, all cameras are processed simultaneously. However, in the `AiWorkers` menu, you can pause the processing of any of the cameras.
        - On the `Settings tab`, processing of all cameras is paused.
        - The video processing is only performed on the currently selected camera tab.

    - Session Saving:
        - The settings from the last session are saved and restored upon the next launch.
        - The application remembers the last opened tab and restores it upon restart.

    - Logging:
        - The application maintains a detailed `log` file, enabling tracking of operations and error detection.

    - YOLOv8-OBB Model Integration:
        - The OBB (Oriented Bounding Box) model is connected and configured for accurate object detection.

    - Frame Interval Processing:
        - The application allows setting a Frame Interval to skip frames, reducing processing load.

    - Result Recording:
        - Detection results can be recorded in a `PostgreSQL` database or in files compatible with `YOLOv6-OBB` (labels.txt and images.jpeg).
        - Recording can be configured based on the model's confidence threshold.

    - Detection Management:
        - The ability to enable or disable detection for each process on the `All Cameras` tab.
        - Supports selecting a detection area with the option to configure processing inside or outside the selected area.

    - Configuration File:
        - The application uses a `JSON` configuration file, allowing flexible settings for:
            - Visibility of the settings tab.
            - Method of saving results (to database or file).
            - Confidence threshold for recording.
            - Use of the model's confidence threshold for recording.

    - Customization for Client Needs:
        - The application has been adapted and refined to meet the specific requirements and tasks of the client.









---------------------------------------------------------------------------------------------------------------
## Project Organization
<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

```
├── main.py            <- This is the main entry point of the project.
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make db' and other
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── db_image       <- Data Base images.
│   ├── images         <- Images.
│   ├── labels         <- Labels.
│   └── video          <- start video and other video.
│
├── docs               <- A default mkdocs project; see mkdocs.org for details
│   ├── docs           <- Docs .md files
|   ├── mkdocs.yml     <- Configuration file MkDocs
|   └── README-DOCS.md <- README MkDocs use
|
├── logs               <- Logs
|
├── models             
|    ├─ weights        <- Trained model file format yolov8n-obb.pt
│    └─ classes.txt    <- Classes for models
│
├── notebooks          <- Jupyter notebooks
│
├── pyproject.toml     <- Project configuration file with package metadata for project
│                         and configuration for tools like black
│
├── src                <- Modules
│   ├── data_type
|   ├── models
|   ├── qt
|   ├── ui
|   └── utils
|
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8, black, isort
```

---------------------------------------------------------------------------------------------------------------



