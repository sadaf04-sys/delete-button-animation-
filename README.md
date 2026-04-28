# Hold to Delete Button Animation

A beautiful, interactive "Hold to Delete" button component with smooth fill animation and tactile feedback. Perfect for destructive actions that require user confirmation.

## Features

✨ **Smooth Fill Animation**
- Pink background fills from left to right over 2000ms
- Rounded left corners, square right edge
- Linear timing for consistent motion

🎨 **Progressive Text Color Change**
- Text color changes letter-by-letter as the fill progresses
- Creates a visual effect of color being "revealed" by the fill
- Staggered animation across all characters

👆 **Tactile Feedback**
- Quick 5% scale down on tap (100ms) for immediate visual feedback
- Smooth scale back to original size (300ms, ease-out)

⚡ **Smooth Release Animation**
- Fill reverses back to the left (300ms, ease-out)
- Button returns to original size simultaneously
- Both animations complete at the same time

## Demo

Open `Animation/delete.html` in your browser to see the button in action.

**To test the interaction:**
1. Click and hold the "Hold to Delete" button
2. Watch the pink background fill from left to right
3. Observe the text color change progressively
4. Release to see the smooth reverse animation

## Animation Specifications

| Animation | Duration | Timing | Direction |
|-----------|----------|--------|-----------|
| Fill | 2000ms | Linear | Left → Right |
| Text Color Change | 2000ms | Linear | Staggered (left to right) |
| Tap Feedback | 100ms | Ease-out | Scale down 5% |
| Release Fill | 300ms | Ease-out | Right → Left |
| Release Scale | 300ms | Ease-out | 0.95 → 1.0 |

## Design System

### Colors
- **Button Background**: `#F0F0F0` (light grey)
- **Fill Color**: `#F9E9EC` (light pink)
- **Text Color (default)**: `#262626` (dark grey)
- **Text Color (filled)**: `#C42742` (red)

### Sizing
- **Button Size**: 158×45px
- **Padding**: 12px all sides
- **Corner Radius**: 32px (left), 0px (right on fill)
- **SVG Icon**: 20×20px

### Typography
- **Font**: Inter, sans-serif
- **Size**: 14px
- **Weight**: 500
- **Text**: "Hold to Delete"

## File Structure

```
delete-button-animation/
├── README.md
├── Animation/
│   ├── delete.html          # Main component file
│   ├── CLAUDE.md            # Design system guidelines
│   └── assets/              # Place SVG icons here
└── .git/                    # Git repository
```

## How It Works

### HTML Structure
- Mobile frame simulation (393×852px)
- Button with SVG trash icon
- Character spans for progressive color animation

### CSS
- Pseudo-element (::before) for the fill effect
- Keyframe animations for fill progression and text color change
- Border-radius adjustment for square right edge

### JavaScript
- Character wrapping for staggered animations
- Event listeners for mousedown/mouseup/mouseleave
- Staggered animation delays based on character position

## Customization

### Change Fill Duration
In `.hold-delete-btn.pressed::before`:
```css
animation: fillWidth 2000ms linear forwards;  /* Change 2000ms to desired duration */
```

### Change Fill Color
In `.hold-delete-btn::before`:
```css
background: #F9E9EC;  /* Change to your desired color */
```

### Change Text
In the HTML button:
```html
<span id="buttonText">Your Custom Text</span>
```

### Adjust Button Size
In `.hold-delete-btn`:
```css
width: 158px;    /* Change width */
height: 45px;    /* Change height */
```

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Notes

- Uses CSS animations and transitions (GPU-accelerated)
- No heavy JavaScript calculations
- Smooth 60fps animations on modern devices
- Optimized for mobile devices

## Future Enhancements

- [ ] Add touch feedback haptics
- [ ] Create React component version
- [ ] Add different animation presets
- [ ] Support custom icons via props
- [ ] Add success/error states after deletion

## Author

Created with Claude Code - AI-powered design engineering

## License

MIT License - Feel free to use in your projects!
