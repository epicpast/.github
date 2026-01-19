---
# Image generation provider
# Options: svg (default), dalle-3, gemini, manual
provider: svg

# SVG-specific settings (only used when provider: svg)
# Options: minimal (default), geometric, illustrated
svg_style: minimal

# Dark mode support
# false = light mode only (default), true = dark mode only, both = generate both variants
dark_mode: false

# Output settings
output_path: .github/social-preview.svg
dimensions: 1280x640
include_text: true
colors: auto

# README infographic settings
infographic_output: .github/readme-infographic.svg
infographic_style: hybrid

# Upload to repository (requires gh CLI or GITHUB_TOKEN)
upload_to_repo: true
---

# GitHub Social Plugin Configuration

This configuration was created by `/github-social:setup` for the **epicpast** organization.

## Current Settings

| Setting | Value | Description |
|---------|-------|-------------|
| Provider | `svg` | Claude generates clean SVG graphics directly |
| SVG Style | `minimal` | Clean design with 3-5 shapes, generous whitespace |
| Dark Mode | `false` | Light mode only |
| Include Text | `true` | Display organization/project name in image |
| Auto Upload | `true` | Automatically upload to repository |

## Provider: SVG (Selected)

Claude generates clean, minimal SVG graphics directly. No API key required.

**Advantages:**
- Free - no API costs
- Instant generation
- Editable - can be modified after creation
- Small file size (typically 10-50KB)
- Crisp at any resolution

**Best for:** Professional, predictable results with consistent branding.

## Alternative Providers

### DALL-E 3
OpenAI's image generation. Requires `OPENAI_API_KEY` environment variable.
- **Pros**: Artistic, creative, varied styles
- **Cost**: ~$0.08 per image
- **Setup**: `export OPENAI_API_KEY=sk-...`

### Gemini
Google's image generation via Gemini API. Requires `GEMINI_API_KEY` environment variable.
- **Models**: `gemini-2.5-flash-image` (fast), `gemini-3-pro-image-preview` (quality)
- **Cost**: ~$0.039 per image
- **Setup**: Get key from [Google AI Studio](https://aistudio.google.com/)

### Manual
Outputs optimized prompts for use with Midjourney, Stable Diffusion, or other tools.

## SVG Style Options

**Minimal** (selected): Clean, simple design with project name and subtle geometric accents. Maximum 3-5 shapes, generous whitespace. Professional and timeless.

**Geometric**: More complex arrangements with 8-15 geometric shapes representing domain metaphors abstractly.

**Illustrated**: Hand-drawn aesthetic using organic SVG paths with warm colors.

## Dark Mode

To enable dark mode variants, change `dark_mode` in the frontmatter:
- `false` - Light mode only (current)
- `true` - Dark mode only
- `both` - Generate both variants:
  - `.github/social-preview.svg` (light)
  - `.github/social-preview-dark.svg` (dark)

## Available Commands

| Command | Description |
|---------|-------------|
| `/github-social:social-preview` | Generate a social preview image |
| `/github-social:readme-enhance` | Enhance README with badges and infographic |
| `/github-social:repo-metadata` | Generate optimized description and topics |
| `/github-social:all` | Run all skills in sequence |
| `/github-social:setup` | Re-run this setup wizard |

Or simply ask naturally: "Generate a social preview for this repo"

## Command Overrides

Override any setting via command flags:
```bash
/social-preview --provider=dalle-3 --dark-mode
/readme-enhance --svg-style=geometric
```

## Notes

- This is a local configuration file (`.local.md` suffix)
- Consider adding to `.gitignore` if you want to keep it private
- API keys should NEVER be stored here - only environment variable names
