# Tutorial_ColabFold_Brev
A step-by-step tutorial for deploying the Jupyter Notebook
[ColabFold v1.5.5: AlphaFold2 using MMseqs2](https://colab.research.google.com/github/sokrypton/ColabFold/blob/main/AlphaFold2.ipynb) on NVIDIA Brev.

### Adavantages of running on Brev
- Brev provides a wide range of GPU types, from older generations like the T4 to advanced ones like the H100. You can find compute configurations that meet your budget and performance goals.
- High-memory GPUs can predict structures for long sequences.
- More powerful GPUs give greater acceleration for structure inference and relaxation.



### Creat Brev Account
Create an account on Brev if you haven't already. You can do this by clicking the “Create an account” button in the top right corner of the [Brev Console](https://console.brev.dev/org/org-2tcmRZuGMBx9Wlh2bxmuIdGb6UN/environments).


### Create Launchable & Deploy Instance
- A "Launchable" is a template of setting up an instance.
- Open a web browser and go to [Brev Console](https://console.brev.dev/org/org-2tcmRZuGMBx9Wlh2bxmuIdGb6UN/environments).
    - Create an account on Brev if you haven't already. You can do this by clicking the “Create an account” button in the top right corner of the Console.
- Click "Launchables" tab in the top menu bar. <br>
<img src="images_brev/tab_launchable.png" alt="Alt text" width="500">

- Click "Create Launchables". <br>
<img src="images_brev/create_launchable.png" alt="Alt text" width="500">

- Here, you can choose from a variety of GPU types for compute configurations. <br>
    Below, I have listed the two compute configurations I tested. <br>
    1. Click "compute" -> "T4" -> "16GiB GPU Memory | 1 GPU • 15GiB RAM • 4 CPUs | GCP • $0.68/hr". <br>
    2. Click "compute" -> "A100" -> "40GiB GPU Memory | 1 GPU • 85GiB RAM • 12 CPUs | GCP • $4.86/hr". <br>
    Going forward, I'll use the T4 configuration as an example. <br>
<img src="images_brev/compute_config_T4.png" alt="Alt text" width="500">

- Type *100* under "Storage (GiB)", then click "Save Compute". <br>
    Note that for certain compute configurations, you cannot select a storage size below the allowed minimum. If, after entering the storage size, the "Save Compute" button does not become active, try adjusting the storage size. <br>
<img src="images_brev/storage_config.png" alt="Alt text" width="500">

- Click "Container" -> Toggle the "Prestall Jupyter" switch to turn it on -> Click "VM Mode" box -> "Save Container".<br>
<img src="images_brev/config_container.png" alt="Alt text" width="500">

- Click "Files" -> Copy & paste the link to the tutorial Jupyter Notebook [AF2_mmseqs2_Brev.ipynb](AF2_mmseqs2_Brev.ipynb) -> Click "Add file". <br>
<img src="images_brev/config_file.png" alt="Alt text" width="500">

- Type under "Name Launchable", e.g., *colabfold-T4* -> Click "Generate Launchable".<br>
<img src="images_brev/name.png" alt="Alt text" width="500"> <br>

- Click "View Launchable". <br>
**Note that now you can copy & paste the link to this Launchable to share it with your friends, including all configurations such as compute, environment, and Jupyter Notebook, to make your work so much more reproducible.** <br>
<img src="images_brev/view_launchable.png" alt="Alt text" width="500">

- Click "Deploy Launchable". <br>
<img src="images_brev/deploy_launchable.png" alt="Alt text" width="500">

- Click "Go to Instance Page" when it becomes available and starts flashing. <br>
<img src="images_brev/go_to_instance_page.png" alt="Alt text" width="500">

- You should now be on the instance page, as shown below. <br>
    - It might take a few minutes before you see the 'Running' status and button "Open Notebook" starts flashing.
    - Under the "Container" tab, you can view the log while your instance is being built. <br>
<img src="images_brev/instance_page_0.png" alt="Alt text" width="500">

- Click on the "Open Notebook" button when it starts flashing. <br>
<img src="images_brev/open_notebook.png" alt="Alt text" width="500">

- You should now be directed to a Jupyter Lab that appears in your web browser. If it doesn’t load, try refreshing the page.<br>
Close up the benign error if it pops up. <br>
<img src="images/path_not_found.png" alt="Alt text" width="300"> <br>
Double click the tutorial Jupyter Notebook `AF2_mmseqs2_Brev` in the left panel to open it up. <br>
<img src="images_brev/click_notebook.png" alt="Alt text" width="500"> <br>

- You're ready to run the tutorial Jupyter Notebook. <br>
<img src="images_brev/ready.png" alt="Alt text" width="500">

### Delete Intance 
After you're done with your instance, make sure you go back to the Instances tab and click the "Delete" button. Otherwise, you'll keep burning your credits. The Instances tab shows all of your running instances.