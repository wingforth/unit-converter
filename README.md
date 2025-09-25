# Unit Converter

A small Flask web application for converting between length, weight, and temperature units.

## Features

- Convert between common length units (mm, cm, dm, m, km, in, ft, yd, mi).
- Convert between common weight units (mg, g, kg, t, oz, lb).
- Convert between temperature units (Celsius, Fahrenheit, Kelvin).
- Simple, responsive UI using vanilla HTML/CSS and Jinja2 templates.

## Requirements

- Python 3.13+
- Flask 3.1.1+
- Recommended: uv

Dependencies are declared in `pyproject.toml`.

## Run the app

```powershell
python run.py
```

Open http://127.0.0.1:5000/ in your browser.

## Project structure

- `app/` - application package
  - `__init__.py` - application factory (imports `app` from `views`)
  - `views.py` - Flask routes and request handlers
  - `measurements.py` - conversion logic and unit definitions
  - `templates/` - Jinja2 HTML templates
  - `static/` - CSS styles
- `run.py` - small runner to start the app
- `pyproject.toml` - project metadata and dependencies

## Testing

Tests are written with `pytest`.

Run tests with:

```powershell
python -m pytest -q
```

The test file is `tests/test_views.py` which exercises the main routes and example conversions.

## Usage notes

- Forms validate numeric input on the server by attempting to coerce `value` to `float` and will show an error message on invalid input.
- Conversion functions live in `app/measurements.py` and are pure functions — easy to unit test.
