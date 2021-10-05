To prevent tests from taking too much time, it is possible to add metadata to the notebook. The .ci/patch_notebooks.py script is run in the CI and  patches the notebooks with the content in the metadata for the cell to be patched.

For example: nr of epochs is changed from 15 to 1 in  301-tensorflow-training-openvino-pot.ipynb by adding  `{"test_replace": {"epochs = 15": "epochs = 1"}` to the cell  metadata of the cell that contains `epochs = 15`. (Test notebooks are written to test_notebookname.ipynb so the patch_notebooks script does not overwrite existing notebooks - this is useful if you want to run this script locally too).

To add metadata to a notebook, click on the gear icon to the right of the notebook in Jupyter Lab. If no metadata exists yet, just create a new dictionary with the `test_replace` key.

![image](https://user-images.githubusercontent.com/77325899/132540921-e931b154-d172-4e00-ac40-ead716989f2d.png)
