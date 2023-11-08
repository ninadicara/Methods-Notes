
Create venv directory
(This used to be a separate package but it included in Python since 3.3)

`python -m venv <myvenv>

Activate: 

`source myvenv/bin/activate`

If using a jupyter notebook with this project, run the following to ensure the venv can be found as a kernel. 

`ipython kernel install --user --name=venv`


Things to do : 

- update pip
- add .gitignore
- git init
- install pandas, jupyter etc
- Set up jupytext
