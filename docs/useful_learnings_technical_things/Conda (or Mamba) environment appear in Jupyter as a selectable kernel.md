To make a Conda (or Mamba) environment appear in Jupyter as a selectable kernel, you need to install ipykernel in the environment and then register it with Jupyter. 
Here’s a step-by-step guide for your xcomet environment.

 Register the environment as a Jupyter kernel:

    ~/miniforge3/bin/mamba run --prefix=~/envs/xcomet/ \
    python -m ipykernel install --user --name xcomet --display-name "Python (xcomet)"

> --name xcomet -> internal kernel name, original env name when the env was created.

> --display-name "Python (xcomet)" -> what shows in Jupyter’s kernel selection dropdown

