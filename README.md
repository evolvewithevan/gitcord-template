# GitCord Template - Monolithic Format

This template has been updated to use the **new monolithic YAML format**. Instead of separate directories and individual YAML files for each channel and category, everything is now contained in a single `template.yaml` file.

## New Template Structure

The template now uses a single `template.yaml` file with the following structure:

```yaml
server:
  name: "Your Server Name"
  version: "2.0"
  description: "Server description"
  releaseNotes: "Release notes"

categories:
  - name: "Category Name"
    position: 0
    type: "category"
    channels:
      - name: "channel-name"
        type: "text"  # or "voice"
        position: 0
        topic: "Channel topic"
        nsfw: false
```

## Usage

1. Clone this template repository to your server:
   ```
   !git clone https://github.com/evolvewithevan/gitcord-template
   ```

2. Apply the template:
   ```
   !git pull
   ```

## Migration from Legacy Format

If you were using the old directory-based format:
- The new format is automatically detected and used
- Legacy commands like `!createchannel` and `!createcategory` will show deprecation warnings
- Use `!git pull` to apply the complete template instead

## Benefits of Monolithic Format

- **Simpler structure**: One file instead of multiple directories
- **Easier editing**: All template configuration in one place
- **Better version control**: Single file changes are easier to track
- **Faster processing**: No need to walk directory structures

## Compatibility

- The system still supports legacy directory-based templates for backward compatibility
- New installations should use the monolithic format
- GitCord will automatically detect and use the appropriate format

## Template Contents

This template includes:

### Boilerplate Category
- **moderator-only**: Private channel for moderators
- **rules**: Server rules and guidelines

### Main Area Category  
- **general**: Main chat channel
- **memes**: Meme sharing channel
- **off-topic**: Casual conversation channel

### Voice Chats Category
- **vc1**: Primary voice channel
- **vc2**: Secondary voice channel (NSFW enabled)
