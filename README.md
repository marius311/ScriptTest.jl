
```julia
# clone repo
git clone https://github.com/marius311/ScriptTest.jl
cd ScriptTest.jl

# install the packages in this repo
julia --project=. -e "using Pkg; Pkg.instantiate()"

# make system image, takes ~2 minutes.
# can be 5-10 minutes for more complex package dependencies
# has to be rerun any time code in any of the packages changes
julia --project=. make_system_image.jl

# run script using system image
julia --startup-file=no --project=. -J Sysimage.so myscript.jl
```