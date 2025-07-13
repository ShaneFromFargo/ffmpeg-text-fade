# FFMPEG Text Fade Generator

A simple web-based GUI tool for generating ffmpeg commands to add text with fade in/out effects to videos.

## 🌐 Live Demo

Visit [https://ffmpeg.shanewhite.co](https://ffmpeg.shanewhite.co) to use the tool online.

## 📝 Description

This tool simplifies the process of creating text overlay effects in videos using ffmpeg. Instead of manually crafting complex ffmpeg commands with alpha channel calculations, this GUI allows you to:

1. Enter your text and customize its appearance
2. Set precise timing for fade-in and fade-out animations
3. Generate a ready-to-use ffmpeg command

## ✨ Features

- **Text Customization**
  - Text content
  - Font size
  - Font file selection
  - Color picker for text color
  - Precise X/Y positioning (with defaults for centered text)

- **Animation Controls**
  - Fade-in start time
  - Fade-in duration
  - Text display duration
  - Fade-out duration

- **User-Friendly Interface**
  - Clean, responsive Bootstrap-based UI
  - Color picker for easy color selection
  - Reset button to clear all fields
  - Immediate command generation

## 🚀 How to Use

1. **Enter File Information**
   - Specify the input video file path
   - Specify the output video file path

2. **Configure Text Properties**
   - Enter the text you want to display
   - Set font size (default: 64)
   - Specify font file (default: Lato-Light.ttf)
   - Choose text color using the color picker
   - Set X/Y positions (defaults to centered)

3. **Set Animation Timing**
   - Fade-in start time (in seconds)
   - Fade-in duration (in seconds)
   - Text display time (in seconds)
   - Fade-out duration (in seconds)

4. **Generate Command**
   - Click "Add Text to Command"
   - Copy the generated ffmpeg command from the output section

5. **Execute the Command**
   - Paste and run the command in your terminal/command prompt
   - ffmpeg will process your video with the specified text effects

## 🛠️ Requirements

- A modern web browser
- ffmpeg installed on your system to execute the generated commands

## 🧰 Technical Details

The generated command uses ffmpeg's drawtext filter with alpha channel manipulation to create smooth fade in/out effects. The alpha value is calculated using conditional expressions based on the timing parameters you provide.

Example of a generated command:
```
ffmpeg -i img.mp4 -filter_complex "[0:v]drawtext=fontfile=Lato-Light.ttf:text='Welcome':fontsize=24:fontcolor=ffffff:alpha='if(lt(t,22),0,if(lt(t,24),(t-22)/2,if(lt(t,29),1,if(lt(t,39),(10-(t-29))/10,0))))':x=(w-text_w)/2:y=(h-text_h)/2" output.mp4
```

## 🧩 Technologies Used

- HTML/CSS/JavaScript
- jQuery
- Bootstrap
- Spectrum.js (color picker)
- Font Awesome icons

## 📋 License

This project is open source and available for personal and commercial use.

## 👨‍💻 Author

Created by Shane White