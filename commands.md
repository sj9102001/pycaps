# Installation (in this repo)
pip install -e ".[all]"
playwright install chromium   # needed for default CSS renderer

# Commands
1. render — Add subtitles to a video


# Basic usage with a built-in template
pycaps render --input my_video.mp4 --template minimalist

# Specify output file
pycaps render --input my_video.mp4 --template minimalist --output output.mp4

# Use a JSON config instead of a template
pycaps render --input my_video.mp4 --config config.json

# Provide an external transcript (skip Whisper transcription)
pycaps render --input my_video.mp4 --template minimalist --transcript transcript.json

# Override styles inline
pycaps render --input my_video.mp4 --template minimalist --style word.color=red

# Preview mode (short low-quality clip, default 0-5s)
pycaps render --input my_video.mp4 --template minimalist --preview
pycaps render --input my_video.mp4 --template minimalist --preview-time=10,15

# Layout options
pycaps render --input my_video.mp4 --template minimalist --layout-align center --layout-align-offset 50

# Whisper options
pycaps render --input my_video.mp4 --template minimalist --lang en --whisper-model base --whisper-prompt "BrandName, TechTerm"
2. template — Manage templates


pycaps template list                           # List all available templates
pycaps template create --name my_template      # Create new template from default
pycaps template create --name my_template --from minimalist  # Copy from existing
3. preview-styles — Preview CSS styles


pycaps preview-styles --template minimalist    # Preview a template's styles
pycaps preview-styles --css my_styles.css      # Preview a custom CSS file
4. config — Manage API key (for AI features)


pycaps config --set-api-key YOUR_KEY
pycaps config --unset-api-key
pycaps config                                  # Show current key
Help

pycaps --help          # Top-level help
pycaps render --help   # Render command help