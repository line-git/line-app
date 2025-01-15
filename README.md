# LINE test files

This repository provides the necessary files to perform tests with
**LINE**. The main repository of **LINE** is available
[here](https://github.com/line-git/line.git).

## Content

The `cards/` folder contains input cards (one for each run), while the
other folders are working directories (one for each topology). DE
matrices and topology-related files (which are the same for every run
involving the same topology) are stored in the `topo-name/common/`
folder, while `topo-name/points/` contains the value of the MIs at
several phase-space points, as well as validation files to verify the
intermediate results of the computations.

Every run can be performed without providing boundary conditions from
the outside. These are indeed generated either with **Expansion by
Regions** (EBR) (input cards with `"ebr"` in the name) or with the
**LINE** implementation of the
[**AMFlow**](https://inspirehep.net/literature/1639025) method (input
cards with `"amf"` in the name). Other runs make use of the results
stored in the `points/` folder as boundary for the propagation.

## Usage

In order to use **LINE** with the tests in this repository:

-   Clone the **LINE** [main
    repository](https://github.com/line-git/line.git) and follow its
    instructions to install dependencies, compile the code and verify
    the installation.

-   Clone this repository with `git clone` in the desired destination
    `path/to/line-app`.

-   Go to the **LINE** directory and create a symbolic link named `app`
    with:

    ``` bash
    cd /path/to/line
    ln -s path/to/line-app app
    ```

    You can replace `app` with any other `link-name`. However, if you do
    so, ensure to include the `--parent-dir link-name` option when
    running `line` (the default value for `--parent-dir` is indeed
    `app`). Similarly, you can avoid creating a symbolic link as long as
    you use `--parent-dir path/to/line-app`.

-   Run `line` using the input cards in the `cards/` directory (see the
    instructions provided in the **LINE** repository to know how to run
    `line`).

For other terminal options, follow the instructions in the main
repository of **LINE**.

## Reference

For a detailed description of the topology, the master integrals and the
kinematic points for each example, refer to our paper:

------------------------------------------------------------------------

R. M. Prisco, J. Ronca, F. Tramontano, *LINE: Loop Integrals Numerical
Evaluation* - [arXiv:2501.01943](https://arxiv.org/abs/2501.01943)

------------------------------------------------------------------------
