![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/logo.jpeg)

<div align="center" style="line-height: 1;">
  <a href="https://www.allvoicelab.com" target="_blank" style="margin: 2px; color: var(--fgColor-default);">
  <img alt="Homepage" src="https://img.shields.io/badge/HomePage-AllVoiceLab-blue?logo=data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0iVVRGLTgiPz4KPHN2ZyBpZD0iX+WbvuWxgl8xIiBkYXRhLW5hbWU9IuWbvuWxgl8xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDM1IDIwIj4KICA8IS0tIEdlbmVyYXRvcjogQWRvYmUgSWxsdXN0cmF0b3IgMjkuNS4xLCBTVkcgRXhwb3J0IFBsdWctSW4gLiBTVkcgVmVyc2lvbjogMi4xLjAgQnVpbGQgMTQxKSAgLS0+CiAgPHBhdGggZD0iTTM0Ljg2LDUuMzFjLjIxLS4zMS0uMDEtLjcyLS4zOC0uNzJoLTIuOThjLS4yNCwwLS40Ni4xMi0uNTkuMzJsLTYuODksMTAuM2MtLjE3LjI2LS41NS4yNi0uNzMsMGwtMi4xNi0zLjExcy0uMDEtLjAyLS4wMi0uMDNMMTMuNjYsMS40Yy0uNTYtLjgtMS40Ny0xLjI2LTIuNDUtMS4yMi0uOTguMDQtMS44NS41Ny0yLjM1LDEuNDFMLjMyLDE2LjIzYy0uNTEuODgtLjQsMS45NC4yOCwyLjcuNzMuODEsMS45NCwxLjA2LDIuOTYuNmwuMTItLjA1LDkuMDMtNS43NGMuOTEtLjU4LDEuOTYtLjg5LDMuMDQtLjkxLjk4LDAsMS45MS40NiwyLjQ4LDEuMjZsMy4xNiw0LjU0Yy41LjcyLDEuMzUsMS4xNSwyLjI3LDEuMTVzMS43Ny0uNDMsMi4yOS0xLjE3bDguOTEtMTMuMzFoMFpNNi41OSwxMi40NWw0LjQyLTcuNTdjLjE3LS4yOS41OC0uMzEuNzctLjAzbDIuNzIsMy45Yy4xOS4yNy4wMy42NC0uMy43LTEuMi4yMS0yLjM1LjY1LTMuMzksMS4zMWwtMy41OSwyLjI4Yy0uNC4yNS0uODctLjItLjYzLS42MWgwWiIvPgo8L3N2Zz4=" style="display: inline-block; vertical-align: middle;"/>
  </a>
  <a href="https://www.allvoicelab.com/docs/introduction" style="margin: 2px;">
    <img alt="API" src="https://img.shields.io/badge/⚡_API-Platform-blue" style="display: inline-block; vertical-align: middle;"/>
  </a>
   <a href="https://github.com/allvoicelab/AllVoiceLab-MCP/blob/main/LICENSE" style="margin: 2px;">
    <img alt="Code License" src="https://img.shields.io/badge/_Code_License-MIT-blue" style="display: inline-block; vertical-align: middle;"/>
  </a>
</div>


<p align="center">

Official AllVoiceLab Model Context Protocol (MCP) server, supporting interaction with powerful text-to-speech and video translation APIs. Enables MCP clients like Claude Desktop, Cursor, Windsurf, OpenAI Agents to generate speech, translate videos, and perform intelligent voice conversion. Serves scenarios such as short drama localization for global markets, AI-Generated audiobooks, AI-Powered production of film/TV narration.

</p>

## Why Choose AllVoiceLab MCP Server?

- Multi-engine technology unlocks infinite possibilities for voice: With simple text input, you can access video generation, speech synthesis, voice cloning, and more.
- AI Voice Generator (TTS): Natural voice generation in 30+ languages with ultra-high realism
- Voice Changer: Real-time voice conversion, ideal for gaming, live streaming, and privacy protection

- Multilingual Dubbing: One-click translation and dubbing for short videos/films, preserving emotional tone and rhythm
- Speech-to-Text (STT): AI-powered multilingual subtitle generation with over 98% accuracy
- Subtitle Removal: Seamless hard subtitle erasure, even on complex backgrounds
- Voice Cloning: 3-Second Ultra-Fast Cloning with Human-like Voice Synthesis 

## Documentation

[中文文档](https://github.com/allvoicelab/AllVoiceLab-MCP/blob/main/doc/README_CN.md)

## Quickstart

1. Get your API key from [AllVoiceLab](https://www.allvoicelab.com/).
2. Install `uv` (Python package manager), install with `curl -LsSf https://astral.sh/uv/install.sh | sh`
3. **Important**: The server addresses of APIs in different regions need to match the keys of the corresponding regions, otherwise there will be an error that the tool is unavailable.

|Region| Global  | Mainland  |
|:--|:-----|:-----|
|ALLVOICELAB_API_KEY| go get from [AllVoiceLab](https://www.allvoicelab.com/workbench/api-keys) | go get from [AllVoiceLab](https://www.allvoicelab.cn/workbench/api-keys) |
|ALLVOICELAB_API_DOMAIN| https://api.allvoicelab.com | https://api.allvoicelab.cn |

### Claude Desktop

Go to Claude > Settings > Developer > Edit Config > claude_desktop_config.json to include the following:
```json
{
  "mcpServers": {
    "AllVoiceLab": {
      "command": "uvx",
      "args": ["allvoicelab-mcp"],
      "env": {
        "ALLVOICELAB_API_KEY": "<insert-your-api-key-here>",
        "ALLVOICELAB_API_DOMAIN": "<insert-api-domain-here>",
        "ALLVOICELAB_BASE_PATH":"optional, default is user home directory.This is uesd to store the output files."
      }
    }
  }
}
```

If you're using Windows, you will have to enable "Developer Mode" in Claude Desktop to use the MCP server. Click "Help" in the hamburger menu in the top left and select "Enable Developer Mode".

### Cursor
Go to Cursor -> Preferences -> Cursor Settings -> MCP -> Add new global MCP Server to add above config.

That's it. Your MCP client can now interact with AllVoiceLab.


## Available methods

| Methods | Brief description |
| --- | --- |
| text_to_speech | Convert text to speech |
| speech_to_speech | Convert audio to another voice while preserving the speech content |
| clone_voice | Create a custom voice profile by cloning from an audio sample |
| remove_subtitle | Remove hardcoded subtitles from a video using OCR |
| video_translation_dubbing | Translate and dub video speech into different languages ​​|
| text_translation | Translate a text file into another language |
| subtitle_extraction | Extract subtitles from a video using OCR |

## Example usage

⚠️ Warning: AllVoiceLab credits are needed to use these tools.

### 1. Text to Speech

Try asking: Convert "At All Voice Lab, we’re reshaping the future of audio workflows with AI-powered solutions, making authentic voices accessible to creators everywhere." into voice.

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/tts_en.png)

### 2. Voice Conversion

After generating the audio from the previous example, select the audio file and ask: Convert this to a male voice.

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/sts_en.png)

### 3. Voice Cloning

Select an audio file with a single voice and ask: Clone this voice.

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/clone_en.png)

### 4. Video Translation

Select a video file (English) and ask: Translate this video to japanese.

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/dubbing_en.png)

Original video: 

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/dubbing_en_ori.png)

After translation: 

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/dubbing_en_result.png)

### 5. Remove Subtitles

Select a video with subtitles and ask: Remove the subtitles from this video.

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/remove_subtitle_en.png)

Original video: 

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/remove_subtitle_en_ori.png)

After the task is completed: 

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/remove_subtitle_en_result.png)

### 6. Text Translation

Select a long text (for example, "The Foolish Old Man Removes the Mountains") and ask: Translate this text to japanese.
If no language is specified, it will be translated to English by default.

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/text_translate_en.png)

### 7. Subtitle Extraction

Select a video with subtitles and ask: Extract the subtitles from this video.

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/subtitle_extract_en.png)

After the task is completed, you will get an SRT file as shown below:

![image](https://github.com/allvoicelab/AllVoiceLab-MCP/raw/main/doc/imgs/subtitle_result_en.png)

## Troubleshooting

Logs can be found at:

- Windows: C:\Users\<Username>\.mcp\allvoicelab_mcp.log
- macOS: ~/.mcp/allvoicelab_mcp.log

Please contact us by email(tech@allvoicelab.com) with log files