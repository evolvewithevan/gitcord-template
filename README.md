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
    type: "category"
    channels:
      - name: "channel-name"
        type: "text"  # or "voice"
        topic: "Channel topic"
        nsfw: false
```

## Position Management

**Positions are automatically determined by the order in the YAML file:**
- Categories are positioned based on their order in the `categories` list
- Channels are positioned based on their order within each category's `channels` list
- No explicit `position` fields are needed - just arrange items in your desired order
- **Existing channels and categories will be automatically reordered** to match the YAML order
- **New channels and categories are created at the correct position** based on their YAML order

### How Position Updates Work

When you run `!git pull`:
1. **Categories** are repositioned to match their order in the YAML file
2. **Channels** within each category are repositioned to match their order in the YAML file
3. **Out-of-order channels are automatically moved** to their correct positions
4. **New channels are created** at the correct position based on their index in the YAML

### Example

If your YAML has:
```yaml
categories:
  - name: "Main Area"      # Will be at Discord position 0
    channels:
      - name: "general"    # Will be at Discord position 0 within category
      - name: "memes"      # Will be at Discord position 1 within category
      - name: "off-topic"  # Will be at Discord position 2 within category
```

Then Discord will display them in exactly this order, regardless of their previous positions.

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
- **Intuitive positioning**: Order in YAML determines Discord position
- **Automatic reordering**: Existing channels moved to match YAML order

## Compatibility

- The system still supports legacy directory-based templates for backward compatibility
- New installations should use the monolithic format
- GitCord will automatically detect and use the appropriate format

## Template Contents

This template includes:

### Boilerplate Category (First)
- **moderator-only**: Private channel for moderators
- **rules**: Server rules and guidelines

### Main Area Category (Second)
- **general**: Main chat channel
- **memes**: Meme sharing channel
- **off-topic**: Casual conversation channel

### Voice Chats Category (Third)
- **vc1**: Primary voice channel
- **vc2**: Secondary voice channel (NSFW enabled) 