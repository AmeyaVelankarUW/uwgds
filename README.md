# omgds

## This is a new version by Ameya from I-tung's parent version. It has a new template file and changes to how subcomponents are imported. It only requires GDSFactory (but GDSHelpers file is kept for history). New components and generators are added. 


The optomechanical graphyical design system (omgds) is a Python package that provides a simple and intuitive way design can optimize integrated optomechanical design layouts. With omgds_py, you can easily create both integrated photonic and electronic circuits, and create a array of different designs to optimize the performance of your optomechanical circuits. This package is based on the [GDSFactory](https://github.com/gdsfactory/gdsfactory) and [gdshelpers](https://gdshelpers.readthedocs.io/en/latest/index.html) package, which are Python packages that provide ways to create GDSII files for use in integrated photonic devices.

## Installation


### Do not do this it probably won't work:
To install omgds.py, simply run the following command:

```baash
pip install omgds
```

### Do this:
Just clone the repository into any folder.

## Usage

Here's a quick example to get you started:

```bash
/Users/[user_name]/opt/anaconda3/bin/python ./omgds_py/main.py
```

Upon running the program, the user will be prompted to enable the GDSFactory (GF) package:

```bash
Enable GF? (yes/y):
```

input ```yes``` or ```y``` to enable the GF package. Otherwise it will default to the gdshelpers package.

Then, it will prompt the user to either save or show the cells.

Input ```show``` to generate a single PCell and it will show the single cell in KLayout.

```bash
Input(save/show, case sensitive):show
```

Input ```save``` to generate PCell arrays and save it in the gds_files directory.

```bash
Input(save/show, case sensitive):save
```

The program is structured as the following:
(here's the list of all the directories and files)

```bash
    .
    ├── omgds_py
    │   ├── __init__.py
    │   ├── main.py
    │   ├── /generators
    │   ├── /subcomponents
    │   ├── /gds_files
    │   ├── /test_paramters
```

Here's a overview of the funcionality of each directory. The main.py file is the main file that runs the program. The generators directory contains the files that generate the cells. The subcomponents directory contains the files that generate the subcomponents of the cells. The gds_files directory contains the gds files that are generated. The test_parameters directory contains the parameters that are used to generate the cells.

### main.py

This is main function that lays out the cells. The user should change the scan_parameters in this `main.py` function. This is the highest level of the omgds design process. Input the scan parameters and the program will generate the cells based on the scan parameters. The user can also input the save or show command to save the cells or show the cells.

### generators

This directoy contains the all the generator for differe chips. Each chip has it's own generator file. The user can add their own generator file to this directory. The user should use each subcompoenets to generate a single cell. After the subcomponents are generated, the user can use translation function to move the subcomponents around to build their on cell.

### subcomponents

This directory contains the basic components that are used in the generator. The user will have the highest degree of freedom in the subcomponents, including changing the metal pad sizes, the waveguide sizes, interdigital transducer (IDT) pitches.

## Contributing

We welcome contributions from the community! If you have any ideas, bug reports, or feature requests, please open an issue on our [GitHub repository](https://github.com/omgds/omgds.py) or submit a pull request.

## License

omgds_py is licensed under the MIT License. See the [LICENSE](https://github.com/omgds/omgds.py/blob/main/LICENSE) file for more information.

## References

The devices in the following papers were created using the omgds_py package:

1. Chen, IT., Li, B., Lee, S. et al. Optomechanical ring resonator for efficient microwave-optical frequency conversion. Nat Commun 14, 7594 (2023). [https://doi.org/10.1038/s41467-023-43393-x](https://www.nature.com/articles/s41467-023-43393-x)

2. N. S. Yama*, I. T. Chen*, et al. “Silicon-Lattice-Matched Boron-Doped Gallium Phosphide: A Scalable Acousto-Optic Platform", Advanced Materials, [doi.org/10.1002/adma.202305434 (2023)](https://onlinelibrary.wiley.com/doi/abs/10.1002/adma.202305434) *equal contribution authors
