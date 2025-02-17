[![GCC](https://github.com/maliput/maliput_documentation/actions/workflows/build.yml/badge.svg)](https://github.com/maliput/maliput_documentation/actions/workflows/build.yml)

# Maliput Documentation

Documentation and Changelog for Maliput & family.

Visit https://maliput.readthedocs.io

## Summary

Maliput's documentation is generated using [readthedocs](https://readthedocs.org/).
The documentation is prepared and served in this repository, in order to be built using [Sphinx](https://www.sphinx-doc.org/en/master/) later on on [readthedocs](https://readthedocs.org/).

Code documentation from all the packages are collected via Doxygen. Those packages are:
 - [maliput](https://github.com/maliput/maliput)
 - [maliput_py](https://github.com/maliput/maliput_py)
 - [maliput_object](https://github.com/maliput/maliput_object)
 - [maliput_object_py](https://github.com/maliput/maliput_object_py)
 - [maliput_malidrive](https://github.com/maliput/maliput_malidrive)
 - [maliput_dragway](https://github.com/maliput/maliput_dragway)
 - [maliput_multilane](https://github.com/maliput/maliput_multilane)
 - [maliput_integration](https://github.com/maliput/maliput_integration)
 - [maliput_integration_tests](https://github.com/maliput/maliput_integration_tests)
 - [delphyne](https://github.com/maliput/delphyne)
 - [delphyne_gui](https://github.com/maliput/delphyne_gui)
 - [delphyne_demos](https://github.com/maliput/delphyne_demos)

The ready-to-build documentation is pushed to `rtd-pages` branch in a daily basis. [readthedocs](https://readthedocs.org/) takes over from there
and updates the online documentation.

## Build documentation

### Requirements

 * Workspace must be created, see [Developer Setup](https://maliput.readthedocs.io/en/latest/developer_setup.html).

__Note:__ As `maliput_documentation` depends on `delphyne` repos mind following the instructions for adding them.

 * Sphinx must be installed, if not:
  ```sh
    apt-get install python3-sphinx
  ```

### Build maliput_documentation package

```sh
  colcon build --packages-up-to maliput_documentation --cmake-args " -DBUILD_DOCS=On"
```
This will prepare and install the files required to later on be built using `sphinx-build`.

### Build Sphinx docs

Run `sphinx-build` command:
```sh
sphinx-build install/maliput_documentation/share/docs output
```

The HTML pages are located in the `output` folder.

## Visualize

To visualize it, open `index.html` using your preferred browser.

_Note:_ If your workspace is containerized, execute the following *outside of your container*. This is because
`xdg-open` is not installed in your container.

From the workspace root:

```sh
xdg-open output/index.html
```

If you encounter an error saying `xdg-open` is not installed, install it using the following:

```sh
sudo apt install xdg-utils
```

## Contributing

Please see [CONTRIBUTING](https://maliput.readthedocs.io/en/latest/contributing.html) page.

## License

[![License](https://img.shields.io/badge/License-BSD_3--Clause-blue.svg)](https://github.com/maliput/maliput_documentation/blob/main/LICENSE)
