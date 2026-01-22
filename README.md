# Landing Page Asset Generator - Claude Code Skill

![Claude Code Nano Banana Logo](generated-assets/logo-modern-minimalist-logo-claude-code-2026-01-22.webp)

A Claude Code skill for generating professional landing page assets using Google's Gemini 3 Pro Image API (playfully called "Nano Banana Pro"). This skill enables Claude to create high-quality marketing visuals, website graphics, and promotional images with automatic prompt enhancement and WebP optimization.

## Features

- **10 Asset Types**: Hero images, product mockups, logos, social banners, and more
- **Automatic Prompt Enhancement**: Follows Gemini best practices for optimal results
- **Smart File Naming**: Generates descriptive filenames based on content
- **WebP Conversion**: Optimized images for web performance
- **Flexible Aspect Ratios**: Support for 10+ common aspect ratios
- **Resolution Options**: 1K, 2K, or 4K output

## Installation

### Prerequisites

- Claude Code CLI installed
- Python 3.7+ with `requests` and `pillow` packages
- Google Gemini API key

### Install the Skill

1. Download the `.skill` file from this repository
2. Install it using Claude Code:

```bash
claude skill install landing-page-asset-generator.skill
```

3. Set your Gemini API key as an environment variable:

```bash
export GEMINI_API_KEY="your-api-key-here"
```

To make it permanent, add to your `~/.bashrc`, `~/.zshrc`, or equivalent:

```bash
echo 'export GEMINI_API_KEY="your-api-key-here"' >> ~/.zshrc
```

### Python Dependencies

The skill requires the following Python packages:

```bash
pip install requests pillow
```

## Usage

Once installed, you can use this skill within Claude Code conversations:

### Basic Usage

```
User: Generate a hero image for a modern SaaS landing page

Claude: I'll use the landing page asset generator skill to create that for you.
```

### Specify Asset Type

```
User: Create a product mockup of a mobile app on an iPhone

Claude: I'll generate a product-type asset with the mobile app mockup.
```

### Custom Parameters

```
User: Make a social media banner for a summer sale, 1:1 aspect ratio, 4K resolution

Claude: I'll create a high-resolution social media graphic for you.
```

## Supported Asset Types

| Type | Description | Default Aspect Ratio |
|------|-------------|---------------------|
| `hero` | Full-width landing page headers | 16:9 |
| `product` | Product mockups, screenshots | 4:3 |
| `logo` | Logos with text rendering | 1:1 |
| `social` | Social media banners | 1:1 |
| `banner` | Promotional banners | 21:9 |
| `feature` | Feature section illustrations | 3:2 |
| `avatar` | Portrait/headshot style images | 1:1 |
| `icon` | App icons, UI icons | 1:1 |
| `illustration` | General illustrations, artwork | 4:3 |
| `other` | Custom - exact prompt, no enhancement | 1:1 |

## Supported Aspect Ratios

`1:1`, `2:3`, `3:2`, `3:4`, `4:3`, `4:5`, `5:4`, `9:16`, `16:9`, `21:9`

## How It Works

1. **User Request**: You describe the asset you need
2. **Claude Analyzes**: Determines appropriate asset type and parameters
3. **Prompt Enhancement**: The skill enhances your prompt with Gemini best practices
4. **Image Generation**: Calls Gemini API to generate the image
5. **Smart Naming**: Creates a descriptive filename based on content
6. **WebP Conversion**: Converts to WebP format for optimal web performance
7. **Saves Output**: Stores in `./generated-assets` directory (or specified location)

## Example Prompts

**Hero Image:**
```
"Create a minimalist workspace scene with a laptop showing an analytics dashboard, soft morning light"
```

**Product Mockup:**
```
"Generate a sleek mobile app mockup on an iPhone, floating with soft shadow on a gradient background"
```

**Logo:**
```
"Design a modern logo for 'TechFlow' with clean sans-serif font and blue gradient"
```

**Social Banner:**
```
"Make an eye-catching '50% OFF' announcement banner with vibrant colors"
```

## Output Format

Generated files follow this naming convention:

```
{type}-{descriptive-slug}-{date}.webp
```

Examples:
- `hero-minimalist-workspace-analytics-2026-01-22.webp`
- `product-iphone-app-mockup-gradient-2026-01-22.webp`
- `logo-techflow-blue-gradient-2026-01-22.webp`

## Advanced Usage

### Direct Script Access

You can also use the Python script directly:

```bash
python landing-page-asset-generator/scripts/generate_asset.py \
  --prompt "Modern SaaS dashboard hero image" \
  --type hero \
  --aspect-ratio 16:9 \
  --resolution 2K \
  --output ./assets \
  --quality 90
```

### Script Parameters

| Parameter | Required | Default | Description |
|-----------|----------|---------|-------------|
| `--prompt` | Yes | - | Image description |
| `--type` | No | `hero` | Asset type |
| `--aspect-ratio` | No | Type default | Override aspect ratio |
| `--resolution` | No | `2K` | `1K`, `2K`, or `4K` |
| `--output` | No | `./generated-assets` | Output directory |
| `--quality` | No | `85` | WebP quality (1-100) |

## Error Handling

The skill includes robust error handling:

- **Missing API Key**: Clear instructions for setup
- **API Rate Limits**: Automatic retry with exponential backoff
- **Invalid Parameters**: Falls back to sensible defaults
- **Generation Failures**: Detailed error messages with API response

## Contributing

Contributions are welcome! If you'd like to improve this skill:

1. Fork the repository
2. Make your changes
3. Submit a pull request

## License

MIT License - feel free to use and modify for your projects.

## Credits

Created for the Claude Code community. Uses Google's Gemini 3 Pro Image API.

## Support

If you encounter issues:

1. Check that your `GEMINI_API_KEY` is set correctly
2. Verify Python dependencies are installed
3. Review the error messages for specific guidance
4. Open an issue on GitHub with details

## Changelog

### v1.0.0
- Initial release
- Support for 10 asset types
- Automatic prompt enhancement
- WebP conversion
- Flexible aspect ratios and resolutions
