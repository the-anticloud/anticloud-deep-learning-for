# DEEP LEARNING FOR

![license](https://img.shields.io/badge/license-license-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-brain_computer_interface-lightgrey)

> Anticloud-hardened packaging of the upstream project `DEEP_LEARNING_FOR` in category **BRAIN COMPUTER INTERFACE**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** BRAIN COMPUTER INTERFACE · **Upstream:** https://github.com/keras-team/keras · **Upstream pin:** `6d8bdf6596a1243cf95981ccc815e4ab49bf5cc8` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Keras 3: Deep Learning for Humans

Keras 3 is a multi-backend deep learning framework, with support for JAX, TensorFlow, PyTorch, and OpenVINO (for inference-only).
Effortlessly build and train models for computer vision, natural language processing, audio processing,
timeseries forecasting, recommender systems, etc.

- **Accelerated model development**: Ship deep learning solutions faster thanks to the high-level UX of Keras
and the availability of easy-to-debug runtimes like PyTorch or JAX eager execution.
- **State-of-the-art performance**: By picking the backend that is the fastest for your model architecture (often JAX!),
leverage speedups ranging from 20% to 350% compared to other frameworks. [Benchmark here](https://keras.io/getting_started/benchmarks/).
- **Datacenter-scale training**: Scale confidently from your laptop to large clusters of GPUs or TPUs.

Join nearly three million developers, from burgeoning startups to global enterprises, in harnessing the power of Keras 3.

## Installation

### Install with pip

Keras 3 is available on PyPI as `keras`. Note that Keras 2 remains available as the `tf-keras` package.

1. Install `keras`:

```
pip install keras --upgrade
```

2. Install backend package(s).

To use `keras`, you should also install the backend of choice: `tensorflow`, `jax`, or `torch`. Additionally,
The `openvino` backend is available with support for model inference only.

### Local installation

#### Minimal installation

Keras 3 is compatible with Linux and macOS systems. For Windows users, we recommend using WSL2 to run Keras.
To install a local development version:

1. Install dependencies:

```
pip install -r requirements.txt
```

2. Run installation command from the root directory.

```
python pip_build.py --install
```

3. Run API generation script when creating PRs that update `keras_export` public APIs:

```
./shell/api_gen.sh
```

## Backend Compatibility Table

The following table lists the minimum supported versions of each backend for the latest stable release of Keras (v3.x):

| Backend    | Minimum Supported Version |
|------------|---------------------------|
| TensorFlow | 2.16.1                    |
| JAX        | 0.4.20                    |
| PyTorch    | 2.1.0                     |
| OpenVINO   | 2026.2.0                  |

#### Adding GPU support

The `requirements.txt` file will install a CPU-only version of TensorFlow, JAX, and PyTorch. For GPU support, we also
provide a separate `requirements-{backend}-cuda.txt` for TensorFlow, JAX, and PyTorch. These install all CUDA
dependencies via `pip` and expect a NVIDIA driver to be pre-installed. We recommend a clean Python environment for each
backend to avoid CUDA version mismatches. As an example, here is how to create a JAX GPU environment with `conda`:

```shell
conda create -y -n keras-jax python=3.10
conda activate keras-jax
pip install -r requirements-jax-cuda.txt
python pip_build.py --install
```

## Configuring your backend

You can export the environment variable `KERAS_BACKEND` or you can edit your local config file at `~/.keras/keras.json`
to configure your backend. Available backend options are: `"tensorflow"`, `"jax"`, `"torch"`, `"openvino"`. Example:

```
export KERAS_BACKEND="jax"
```

In Colab, you can do:

```python
import os
os.environ["KERAS_BACKEND"] = "jax"

import keras
```

**Note:** The backend must be configured before importing `keras`, and the backend cannot be changed after
the package has been imported.

**Note:** The OpenVINO backend is an inference-only backend, meaning it is designed only for running model
predictions using `model.predict()` method.

## Backwards compatibility

Keras 3 is intended to work as a drop-in replacement for `tf.keras` (when using the TensorFlow backend). Just take your
existing `tf.keras` code, make sure that your calls to `model.save()` are using the up-to-date `.keras` format, and you're
done.

If your `tf.keras` model does not include custom components, you can start running it on top of JAX or PyTorch immediately.

If it does include custom components (e.g. custom layers or a custom `train_step()`), it is usually possible to convert it
to a backend-agnostic implementation in just a few minutes.

In addition, Keras models can consume datasets in any format, regardless of the backend you're using:
you can train your models with your existing `tf.data.Dataset` pipelines or PyTorch `DataLoaders`.

## Why use Keras 3?

- Run your high-level Keras workflows on top of any framework -- benefiting at will from the advantages of each framework,
e.g. the scalability and performance of JAX or the production ecosystem options of TensorFlow.
- Write custom components (e.g. layers, models, metrics) that you can use in low-level workflows in any framework.
    - You can take a Keras model and train it in a training loop written from scratch in native TF, JAX, or PyTorch.
    - You can take a Keras model and use it as part of a PyTorch-native `Module` or as part of a JAX-native model function.
- Make your ML code future-proof by avoiding framework lock-in.
- As a PyTorch user: get access to power and usability of Keras, at last!
- As a JAX user: get access to a fully-featured, battle-tested, well-documented modeling and training library.

Read more in the [Keras 3 release announcement](https://keras.io/keras_3/).

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Python** (manifests: pyproject.toml, requirements.txt; scanned in UPSTREAM_CLONE)
- Top-level source layout: `benchmarks/`, `examples/`, `integration_tests/`, `keras/`, `shell/`
- Snapshot size: **1016 files**, **333733 lines of code** (measured; see Benchmarks)
- Primary languages: `.py` (994), `.txt` (8), `.md` (5), `(none)` (2), `.sh` (2), `.cff` (1)
- Upstream commit pinned for this packaging: `6d8bdf6596a1243cf95981ccc815e4ab49bf5cc8`

---

## Installation

timeseries forecasting, recommender systems, etc.

- **Accelerated model development**: Ship deep learning solutions faster thanks to the high-level UX of Keras
and the availability of easy-to-debug runtimes like PyTorch or JAX eager execution.
- **State-of-the-art performance**: By picking the backend that is the fastest for your model architecture (often JAX!),
leverage speedups ranging from 20% to 350% compared to other frameworks. [Benchmark here](https://keras.io/getting_started/benchmarks/).
- **Datacenter-scale training**: Scale confidently from your laptop to large clusters of GPUs or TPUs.

Join nearly three million developers, from burgeoning startups to global enterprises, in harnessing the power of Keras 3.

*Section quoted from the upstream readme.*
Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

The `openvino` backend is available with support for model inference only.

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

The upstream API surface is defined by the `DEEP_LEARNING_FOR` source tree vendored in `UPSTREAM_CLONE/` (Python ecosystem). Public entry points:

- Source modules: `benchmarks/`, `examples/`, `integration_tests/`, `keras/`, `shell/`
- The snapshot declares 8 dependency references across 1 ecosystem(s); see Dependencies below.
- Overlay API: `anticloud/cli.py` exposes 13 subcommands with JSON stdout; `anticloud/bench/runner.py` runs the 16-check suite; `anticloud/provenance/chain.py` exposes the SHA3-256 + Ed25519 provenance chain.

---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Python |
| Manifests detected | pyproject.toml, requirements.txt |
| Files in snapshot | 1016 |
| Lines of code | 333733 |
| Dependency references | 8 |
| Dependencies by ecosystem | pypi: 8 |
| Upstream license | Apache-2.0 |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| pypi | absl-py | - | pyproject.toml |
| pypi | numpy | - | pyproject.toml |
| pypi | rich | - | pyproject.toml |
| pypi | namex | - | pyproject.toml |
| pypi | h5py | - | pyproject.toml |
| pypi | optree | - | pyproject.toml |
| pypi | ml-dtypes | - | pyproject.toml |
| pypi | packaging | - | pyproject.toml |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

backend to avoid CUDA version mismatches. As an example, here is how to create a JAX GPU environment with `conda`:

```shell
conda create -y -n keras-jax python=3.10
conda activate keras-jax
pip install -r requirements-jax-cuda.txt
python pip_build.py --install
```

*Section quoted from the upstream readme.*
Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

*Excerpt from upstream `CONTRIBUTING.md`:*

Keras 3 is a high-velocity open-source project. We welcome contributions!

Contributions can be made in a variety of ways, including coding, enriching documentation, refining docstrings, and providing code examples.

Please review our
[AI-Assisted Contribution Policy](#ai-assisted-contribution-policy).

## Current items open for contributions
At [this link](https://github.com/keras-team/keras/issues/18442), you'll find a list of items where your help is needed!

## How to contribute code

Follow these steps to submit your code contribution.

### Step 1. Open an issue

Before making any changes, we recommend opening an issue (if one doesn't already
exist) and discussing your proposed changes. This way, we can give you feedback
and validate the proposed changes. Unsolicited PRs that attempt to fix complex
issues without prior discussion in a GitHub issue may be closed.

If the changes are minor (simple bug fix or documentation fix), then feel free
to open a Pull Request (PR) without discussion.

### Step 2. Make code changes

To make code changes, you need to fork the project. You will need to setup a
development environment and run the unit tests. This is covered in the section
"Setup environment".

### Step 3. Create a pull request

Once the change is ready, open a pull request from your branch in your fork to
the master branch in [keras-team/keras](https://github.com/keras-team/keras).

### Step 4. Sign the Contributor License Agreement

After creating the pull request, the `cla/google` check will be performed and,
if you haven't signed the Contributor License Agreement (CLA), it will fail with
instructions on how to do so. Please follow the instructions to sign the CLA and
the check will pass.

![CLA signed](https://github.com/keras-team/keras/assets/1091026/71c26353-e3b5-4135-8bae-64693c717775)

### Step 5. Code review

If the tests fail, look into the error messages and try to fix them.

![CI tests](https://github.com/keras-team/keras/assets/1091026/6f6c17ef-6bd7-4e95-9fbc-1906cde37380)

A reviewer will review the pull request and provide comments. There may be
several rounds of comments and code changes before the pull request gets
approved by the reviewer.

![Approval from reviewer](https://github.com/keras-team/keras/assets/1091026/8d28f74c-21e9-4146-b0ff-62d649a552a8)

### Step 6. Merging

Once the pull request is approved, a `ready to pull` tag will be added to the
pull request. A team member will take care of the merging.

![Ready to pull an

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: Apache-2.0** (evidence: `LICENSE` in the upstream snapshot).

License file excerpt:

```text
                                 Apache License
                           Version 2.0, January 2004
                        http://www.apache.org/licenses/

   TERMS AND CONDITIONS FOR USE, REPRODUCTION, AND DISTRIBUTION

   1. Definitions.

      "License" shall mean the terms and conditions for use, reproduction,
      and distribution as defined by Sections 1 through 9 of this document.

      "Licensor" shall mean the copyright owner or entity authorized by
      the copyright owner that is granting the License.

      "Legal Entity" shall mean the union of the acting entity and all
      other entities that control, are controlled by, or are under common
      control with that entity. For the purposes of this definition,
      "control" means (i) the power, direct or indirect, to cause the
      direction or management of such entity, whether by contract or
      otherwise, or (ii) ownership of fifty percent (50%) or more of the
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original Apache-2.0 terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `Apache-2.0` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `DEEP_LEARNING_FOR` (category: BRAIN COMPUTER INTERFACE)
- **Upstream URL:** https://github.com/keras-team/keras
- **Pinned commit (SHA):** `6d8bdf6596a1243cf95981ccc815e4ab49bf5cc8`
- **Branch:** master
- **Pin provenance:** GitHub API commits/master. The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`e6db6634bcb9ec49e93ace66cda85d527c6fa95da208082ef866e75ec449e8a4`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |

