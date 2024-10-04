# Creating a Custom Gauge Widget with PyQt5

This code defines a highly customizable circular gauge widget implemented using PyQt5 to create a customizable circular gauge widget that mimics an analog voltage meter.
The core component is the CircularGauge class, which inherits from QWidget and uses QPainter for rendering. The gauge features a configurable arc with customizable start and end angles, dynamic tick marks and numbers, and a smooth-moving needle with shadow effects. Key functionalities include value range management, antialiased rendering, and customizable visual elements (colors, thickness, fonts). The implementation uses trigonometric calculations to position elements and includes a slider-based demo interface through the Windows class.

![Circular Gauge Widget Preview](https://github.com/user-attachments/assets/3c724b50-0ba6-4ac7-8c87-89543f96718f)

## Features

- Customizable minimum and maximum values
- Adjustable start and end angles for the gauge arc
- Configurable number of steps/ticks
- Customizable colors for all components:
  - Outer circle (pen and brush colors)
  - Inner ring (pen and brush colors)
  - Inner circle (brush color)
  - Ticks and numbers
- Dynamic needle movement with shadow effects
- Antialiasing for smooth rendering
- Responsive design that scales with widget size
- Interactive slider control for value adjustment

## Installation

### Prerequisites

- Python 3.6+
- PyQt5

```bash
pip install PyQt5
```

### Basic Usage

```python
from PyQt5.QtWidgets import QApplication
from PyQt5.QtGui import QColor
import sys
from circular_gauge import CircularGauge, Windows

# Create basic gauge
app = QApplication(sys.argv)
window = Windows()
window.show()
sys.exit(app.exec_())
```

### Advanced Usage

```python
from PyQt5.QtGui import QColor
from circular_gauge import CircularGauge

# Create customized gauge
gauge = CircularGauge(
    min_value=0,
    max_value=30,
    value=0,
    steps=15,
    start_angle=-210.0,
    end_angle=30.0,
    outer_circle_pen_color=QColor(137, 148, 153),
    outer_circle_brush_color=QColor(100, 100, 100, 255),
    outer_circle_thickness=14,
    inner_ring_pen_color='darkred',
    inner_ring_brush_color='red',
    inner_circle_brush_color=QColor(100, 100, 100, 255),
    number_font_size=14,
    number_font_family='Arial'
)
```

## API Reference

### CircularGauge Class

#### Constructor Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| min_value | float | 0.0 | Minimum value of the gauge |
| max_value | float | 100.0 | Maximum value of the gauge |
| value | float | 50.0 | Initial value of the gauge |
| steps | int | 10 | Number of major ticks on the gauge |
| start_angle | float | -210.0 | Starting angle in degrees |
| end_angle | float | 30.0 | Ending angle in degrees |
| outer_circle_pen_color | QColor/str | Qt.black | Color of the outer circle border |
| outer_circle_brush_color | QColor/str | None | Fill color of the outer circle |
| outer_circle_thickness | int | 12 | Thickness of the outer circle |
| inner_ring_pen_color | QColor/str | Qt.black | Color of the inner ring border |
| inner_ring_brush_color | QColor/str | Qt.white | Fill color of the inner ring |
| inner_circle_brush_color | QColor/str | None | Fill color of the center circle |
| number_font_size | int | 10 | Font size for gauge numbers |
| number_font_family | str | 'Arial' | Font family for gauge numbers |

#### Methods

| Method | Parameters | Return Type | Description |
|--------|------------|-------------|-------------|
| setValue | value: float | None | Sets the current value of the gauge |
| normalize_angle | angle: float | float | Normalizes an angle to the range [0, 360) |

## Customization Examples

### Modern Dark Theme
```python
gauge = CircularGauge(
    outer_circle_pen_color=QColor(50, 50, 50),
    outer_circle_brush_color=QColor(30, 30, 30),
    inner_ring_pen_color=QColor(70, 70, 70),
    inner_ring_brush_color=QColor(40, 40, 40),
    inner_circle_brush_color=QColor(20, 20, 20)
)
```

### Classic Voltage Meter
```python
gauge = CircularGauge(
    outer_circle_pen_color='black',
    outer_circle_brush_color='white',
    inner_ring_pen_color='darkred',
    inner_ring_brush_color='red',
    number_font_family='Times New Roman'
)
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Inspired by analog voltage meters and modern gauge designs
- Built with PyQt5 for robust cross-platform compatibility

## Author

Yamil Garcia

## Support

For support, please open an issue in the GitHub repository.
