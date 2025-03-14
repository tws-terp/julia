# Julia commands

] i		Enter package mode
; 		Enter shell mode
names(Main)	List all the modules in Main

# Getting Started

To create a new Julia software project follow these steps. Note that some of this can be done with VS Code extensions, but we will do them at the command line level here.

Create a new project and start Julia.

```
$ cd <demo>
$ julia
julia>
```
Next we use the Julia package manager ```Pkg``` to set up the environment and create a project template ("demo").

```
julia> ]
(@v1.11) pkg>
(@v1.11) pkg> generate demo
  Generating  project demo:
    demo/Project.toml
    demo/src/demo.jl
(@v1.11) pkg> activate demo
  Activating project at `~/projects/julia/demo`

(demo) pkg>
```

Next you can add the packages that your project will use.

```
(demo) pkg> add CSV
    Updating registry at `~/.julia/registries/General.toml`
	...
Precompiling project...
  10 dependencies successfully precompiled in 25 seconds. 20 already precompiled.

(demo) pkg> 
(demo) pkg> status
Project demo v0.1.0
Status `~/projects/julia/demo/Project.toml`
  [336ed68f] CSV v0.10.15
(demo) pkg> 
```

# Activating a project environment (from command line)

Now that an project environment has been created you can activate it and try it out as follows.

```
$ cd demo
$ julia --project=.
julia> include("src/demo.jl") # Load the source code containing module "demo" and function "greet"
julia> using .demo # Load the module
julia> greet("Joe") # Execute the function
Hello Joe. Welcome to Julia!
julia> 
```

# Activating a project environment from VS Code

Install the Julia extension

Open the project folder (e.g. demo)

Open a terminal window to run the REPL

Select the code you want to run and then execute (CTL/CMD-SHIFT-P) the following:

"Julia:Execute active file via REPL"

```
Main.demo
julia> greet("Joe") 
Hello Joe. Welcome to Julia!
julia>
```
