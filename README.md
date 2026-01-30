# Image Filtering and Processing Application

This project is an image filtering and transformation application designed to demonstrate core image processing techniques and interactive editing features. The application enables users to apply visual effects, perform geometric transformations, and manage editing history in a non-destructive manner.

## Features

### Image Editing
- **Edge Detection**  
  Applies edge detection algorithms to identify significant intensity changes within an image, producing a high-contrast outline effect useful for both visual analysis and artistic styling.

- **Color Transformations**  
  Supports multiple color filters such as vintage, grayscale, and other stylized effects by manipulating pixel color channels and applying color transformation matrices.

- **Image Flipping**  
  Allows horizontal and vertical image flipping through coordinate remapping, enabling basic geometric transformations of image orientation.

### State Management
- **Undo Functionality**  
  Maintains a stack-based history of image states, allowing users to revert to previous edits instantly. This ensures non-destructive editing and encourages experimentation.

- **Save Functionality**  
  Exports the current image state to disk in a standard image format, preserving all applied filters and transformations.

## Technical Overview

Images are loaded into memory and represented as a mutable pixel array. Each filter or transformation generates a new image state rather than modifying the original image directly. The resulting image is pushed onto an undo stack and rendered to the user interface.

### Image Processing Pipeline
1. Load image and convert it into a pixel-based representation  
2. Apply selected filter or transformation  
3. Store the resulting image in a history stack  
4. Render the updated image to the interface  

This pipeline ensures consistent behavior across operations and enables reliable undo functionality.

### Algorithms and Techniques
- **Edge Detection**: Gradient-based intensity comparison to detect image edges  
- **Color Filters**: Per-pixel color channel manipulation and color matrix transformations  
- **Flipping**: Pixel coordinate remapping along horizontal or vertical axes  
