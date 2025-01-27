# Python Clock Poetry Requirements Buildpack

This buildpack installs Python requirements using Poetry for the clock process in a Heroku application.

## Usage

Add this buildpack to your Heroku application:

```
heroku buildpacks:add https://github.com/nesbtesh/poetry-subdirectory-heroku-buildpack.git
```

Make sure you have a `pyproject.toml` file in your `apps/clock` directory.

## Structure

- `bin/detect`: Checks for the presence of apps/clock/pyproject.toml
- `bin/compile`: Installs Poetry and project dependencies
- `bin/release`: Provides default process types

## Requirements

Your apps/clock directory should contain:
- pyproject.toml
- poetry.lock

The buildpack will:
- Install Poetry
- Configure Poetry to not create virtual environments (as Heroku handles this)
- Install project dependencies