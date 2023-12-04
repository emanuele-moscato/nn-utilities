# `nn-utilities` package

Package with utility modules (implementing functions and classes) to work with
neural networks (with Tensorflow/Keras for now).

Modules:
- `keras_utilities.py`: module containing utilities to work with keras models (plotting, managing training history etc.).

- `tfp_utilities.py`: module containing utilities to work with Tensorflow Probability models (making predictions with Bayesian NN, extracting uncertainties etc.).

## Installation

The `nn-utilities` package can be installed in two ways.

### Installation by cloning the repo

Clone the repository locally,
```
git clone git@github.com:emanuele-moscato/nn-utilities.git
```
The repository is not in the repo's root directory, but rather in the `nn_utilities` subdirectory (notice the underscore w.r.t. the name of the repo and the package). Navigate into that and install with Pip:
```
cd nn-utilities/nn_utilities
pip install .
```

If you plan to modify the source code locally, you can install with Pip in **developer mode** so that you don't have to reinstall the package to see changes. To do that, follow the instructions above but install with the `-e` option:
```
pip install -e .
```

### Installation from the GitHub repo

The package can be installed from GitHub directly, without explicitly cloning the repo (pip does it anyway under the hood, but the user doesn't have to know anything about it). To do this, execute
```
pip install 'git+ssh://git@github.com/emanuele-moscato/nn-utilities.git@main#subdirectory=nn_utilities'
```

This tells Pip to install the package found in the `nn_utilities` subdirectory of the repo, looking at the latest version currently in the `main` branch. For completeness, the general syntax is
```
pip install 'git+ssh://git@github.com/<user>/<repo>.git@<branch>#subdirectory=<subdir>'
```

**Note:** `<branch>` can even point to the identifier of a specific commit, in case a particular version needs to be installed.

If the version in the specified branch of the repo changes, the installation can be updated by adding the `-U` option to the Pip command,
```
pip install -U 'git+ssh://git@github.com/emanuele-moscato/nn-utilities.git@main#subdirectory=nn_utilities'
```

## Testing

After the installation, some manual testing can be done via the noteboos provided in the `notebooks/` subdirectory of the repo's root. However, better testing can be achieved by using `nose2`, which is installed as part of the package's requirements.

Testing with `nose2` happens by automatically executing all Python scripts with filename matching the `test*.py` structure, which are placed in the `tests/` subdirectory. These script use the `unittest` library to write test cases and `nose2` is 100% compatible with this. Tu run the tests with `nose2`, navigate to the package's directory (`nn_utilities`, where the `tests/` directory is) and execute
```
nose2
```

**Note:** there's no guarantee on test coverage - this will probably remain as an example of how testing can be done in principle!
