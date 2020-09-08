# Presentation

Drag "`getting_data_with obj_tables.svg`" into your browser and use left and right to navigate though the slides. Hit `i` to view index.

Made with JessyInk in Inkscape.

# Example Data

- in folder "`examples`"

## Commands (using docker)

The example process was done as follows:
1. File `01_created_schema.xlsx` was created by hand.
2. File `02_generated_uml.svg` was generated to look at the dependencies.
3. File `03_generated_template.xlsx` was generated. This is the Template to fill out.
4. The Template was copied and renamed to `04_template_filled_with_data.xlsx`. This File was filled with valid example data.

```sh
# get docker image (~1GB)
docker pull karrlab/obj_tables

# validate schema
docker run -v ${PWD}/.:/opt/input karrlab/obj_tables:latest validate /opt/input/01_created_schema.xlsx /opt/input/01_created_schema.xlsx

# generate UML
docker run -v ${PWD}/.:/opt/input karrlab/obj_tables:latest viz-schema /opt/input/01_created_schema.xlsx /opt/input/02_generated_uml.svg

# generate template
docker run -v ${PWD}/.:/opt/input karrlab/obj_tables:latest gen-template /opt/input/01_created_schema.xlsx /opt/input/03_generated_template.xlsx

# validate data+schema
docker run -v ${PWD}/.:/opt/input karrlab/obj_tables:latest validate /opt/input/01_created_schema.xlsx /opt/input/04_template_filled_with_data.xlsx
```

# obj_tables-Links
- Homepage: https://objtables.org/
- Documentation: https://www.objtables.org/docs
- Tech. documentation: https://docs.karrlab.org/obj_tables/master/1.0.9/index.html
- Jupyter Tutorials: https://sandbox.karrlab.org/tree/obj_tables
- Quick Start Guide: https://www.objtables.org/guide
- Resources
    - Web application: https://www.objtables.org/app
    - Web service: https://www.objtables.org/api
    - Command-line program: https://pypi.org/pypi/obj_tables
    - Python package: https://pypi.org/pypi/obj_tables
    - Dockerfile: https://github.com/KarrLab/obj_tables/blob/master/Dockerfile
    - Source Code: https://github.com/KarrLab/obj_tables


# License

all Data [CC-BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
