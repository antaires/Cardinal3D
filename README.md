# Stanford CS248 Assignment 2: MeshEdit

We have created a [Wiki](https://stanford-cs248.github.io/Cardinal3D/) that will be the primary source of information about this assignment. On that page you will find all the details about what you need to implement, etc. This document only contains administrative details about building the starter code, grading, and submission.

## Due Date

The assignment is due Feb. 11 at 11:59:59 PM.

## Code Environment

This codebase should compile on Linux, Mac OS X, and Windows on a typical environment. Check out the [git setup page](https://stanford-cs248.github.io/Cardinal3D/git/) and [the project page](https://stanford-cs248.github.io/Cardinal3D/build/) to set up the github repo, install dependencies and building the code. 

When you have successfully built your code, you should get an executable named `Cardinal3D`. Upon starting the program, it should be in model mode. The [User Guide](https://stanford-cs248.github.io/Cardinal3D/guide/) details how to use the interface. 


## Evaluation
For this assignment, you will implement methods in `meshEdit.cpp`.

The User Guide on the wiki describes a large number of features that are in principle available in MeshEdit mode. You do not have to implement all of these features to receive full credit on the assignment! However, you do have to successfully implement a subset of the features. Implementing additional features beyond the required subset will earn you extra credit points.

The particular requirements, and the percentage of the grade (100 pts total) they correspond to, are:

* Four of the local operations: **EdgeCollapse**, **EdgeFlip**, **EdgeSplit** and **FaceBevel** (10 pts each)
* Three of the global operations: **Triangulation**, **LinearSubdivision**, and **CatmullClarkSubdivision** (10 pts each)
* One of: **LoopSubdivision**, **IsotropicRemeshing**, or **Simplification** (10 pts)
* Create one beautiful 3D model using Cardinal3D (15 pts)
* Submit a suggested improvement to the assignment documentation on Piazza (5 pts)


In other words, everyone has to implement **EdgeCollapse**, **EdgeFlip**, **EdgeSplit**, **FaceBevel**, **Triangulation**, **LinearSubdivision**, and **Catmull-Clark**. These features are the bare minimum needed to model interesting subdivision surfaces; **Triangulation** is necessary in order to do the global remeshing task(s). Note that some of the global tasks require that you implement specific local operations! For instance, the implementation of **Simplification** depends on **EdgeCollapse**. In summary, we list all the local operations as follows (these operations are described in the User Guide):

* **VertexBevel**
* **EdgeBevel**
* **FaceBevel** - everyone must implement
* **EraseVertex**
* **EraseEdge**
* **EdgeCollapse** - everyone must implement
* **FaceCollapse**
* **EdgeFlip** - everyone must implement
* **EdgeSplit** - everyone must implement

The global operations, and their dependency on local operations, are as follows:

* **Triangulation** - everyone must implement
* **LinearSubdivision** - everyone must implement
* **CatmullClarkSubdivision** - everyone must implement
* **LoopSubdivision** - depends on **EdgeSplit** and **EdgeFlip**
* **IsotropicRemeshing** - depends on **EdgeSplit**, **EdgeFlip**, and **EdgeCollapse**
* **Simplification** - depends on **EdgeCollapse**

You are free to change the subset of features you choose to implement at any point during the assignment, but you should clearly indicate which features you chose (including those implemented for extra credit) by putting this information in your writeup (described below). You might find it worthwhile using the checkConsistency member function of the HalfedgeMesh class to help debug your operations.

Extra credit: each additional local operation beyond the requirements will be worth 2 pts; each additional global operation will be worth 4 pts. The maximum possible grade on the assignment is 110 pts.

#### America's Next Top 3D Model
Every student is required to submit a 3D model created from cube.dae using their implementation of Cardinal3D, which will be automatically entered into a class-wide 3D modeling competition. Models will be critiqued and evaluated based on both technical sophistication and aesthetic beauty. Note: Use of any other 3D package (e.g., free or commercial 3D modelers like Maya or Blender) is strictly prohibited! This model must be created by opening cube.dae, applying the operations implemented as part of the assignment, and saving the result.

NOTE: We are expecting some high-quality output here---or at least some creativity! Don't just brush this one off. :-)

Include this model in the root directory of your submission as model.dae.

#### Documentation
Clear, well-written documentation is a critical part of software development. Since you (the students) are the ones who will most benefit from good documentation---or will suffer through bad documentation---we are "crowd sourcing" improvements to the course material. What did you find confusing---and then finally figure out?

As 5% of your assignment grade, you will need to submit suggested edits to the assignment documentation. These could be:

* Suggested changes or additions to the assignment handout
* Suggested changes or additions to assignment Wiki 
* Suggested changes or additions to comments in the skeleton code

Do not wait until the due date to submit these suggested edits. They will be most helpful to your classmates (and to us!) if they are submitted ahead of time, so that we can immediately incorporate any good suggestions into the actual course material. To submit your edits, you must therefore:

* Go on Piazza
* Attach the thread with the label **a2wiki**
* Make an anonymous (not private) post with your suggested edit

The TAs will monitor this label, and immediately update the docs with any/all useful suggestions. This Piazza post will also be recorded as part of your assignment grade. Note that we do not have to accept your edit in order for you to receive full credit on the assignment. However, we will grade your edits based on whether they appear to be a "good faith effort" to make a useful comment. In other words, did you really think about what is clear/unclear and provide a useful edit? Or did you just write something totally random at the very last minute? :-) Especially useful edits (e.g., those that provide nice insights, or point out serious bugs/errors) may receive extra credit.

## Writeup
Additionally, you will submit a short document explaining what you have implemented, and any particular details of your submission. If your submission includes any implementations which are not entirely functional, please detail what works and what doesn't, along with where you got stuck. This document does not need to be long; correctly implemented features may simply be listed, and incomplete features should be described in a few sentences at most.

The writeup must be a pdf, markdown, or plaintext file. Include it in the root directory of your submission as writeup.pdf, writeup.md, or writeup.txt.

Failure to submit this writeup will incur a 10 pts penalty on the assignment.

## Submission Instructions
We are using [Canvas](https://canvas.stanford.edu) as our submission tool. You should create and upload a zipped folder of your entire `/src` subdirectory along with the writeup (e.g. writeup.txt) and 3D modeling submission (`model.dae`). Do not include your build subdirectory. You may work in teams of up to two people. If working in a team, please have only one person make the submission. 

## Acknowledgement

CS248 course staff would like to thank Professor Keenan Crane and his course assistants for the initial development of assignment materials.