# Writing Reusable Code in Julia - Carlos Paniagua

### Use case

-   You are working on a research project that requires computation. 💻👩‍💻

-   You write your code; you test it (👍) and it just works! 🚀

-   You decide your code is general enough that it could be useful for solving related problems. 🤓

-   You add some documentation and host your code in some public repository and tell other people about it. 🎤

-   Other people realize your code could be useful to solve their problems! 😎

-   They take your code, try to use it and... it doesn't work 😱

-   If they're lucky, the code "might work" but the results are not the expected ones 😱😱

This is a very common problem in the scientific research community. Here we present an introduction about best practices to building reusable code in the Julia ecosystem.

## Our definition of reusable code

[Reusable code](https://en.wikipedia.org/wiki/Reusability) is code that is easy to distribute and use (correctly and consistently).

> [!NOTE]
> If you'd like to follow along with the rest of the discussion, you'll need Git, a text editor or IDE (VS Code recommended with the Julia extension) and Julia (naturally).

To write reusable Julia code we need to understand how to *manage dependencies* in Julia.

## Managing Dependencies

A dependency (dep) is code other people (even ourselves) wrote and we are using in a project.

Let's add some deps to our base Julia installation using Julia's Package Manager.

1.  Add a few deps with the `add` command

    ``` julia
    $ julia
    julia> # get to pkg mode with `]`
    (@v1.9) pkg> add Example StaticArrays # add the `Example` and `StaticArrays` packages
    ```

2.  Look at the deps in your base Julia with the `status` or `st` command

    ``` julia
    (@v1.9) pkg> status
    Status `C:\Users\cpaniagu\.julia\environments\v1.9\Project.toml`
    [7876af07] Example v0.5.3
    [90137ffa] StaticArrays v1.6.3
    ```

3.  Remove a dep with `rm`

    ``` julia
    (@v1.9) pkg> rm StaticArrays
    ```

4.  Seeing is believing: look at your deps again

    ``` julia
    (@v1.9) pkg> st # and be lazy
    Status `C:\Users\cpaniagu\.julia\environments\v1.9\Project.toml`
    [7876af07] Example v0.5.3
    ```

## Make a package!

A package is code with structure that leverages available tooling for efficient distribution and use. We could add this structure to our code manually but there is tooling for this already! 🛠️

Some options

-   Use `Pkg.generate` for a bare-bones package structure
-   Use [PkgTemplates.jl](https://github.com/JuliaCI/PkgTemplates.jl) for more features (Readme, License, Documentation, test suite, CI and more)
-   Clone some base repo and customize to your needs ([Example.jl](https://github.com/JuliaLang/Example.jl), [MyAwesomePackage.jl](https://github.com/sylvaticus/MyAwesomePackage.jl))

For the rest of the discussion we'll use `generate` from the Julia package manager.

1.  Navigate to where you want to your project/package.

2.  From Julia's package manager issue `generate MyPackage`

    ``` julia
     (@v1.9) pkg> generate MyPackage
    ```

    You will see a new folder `MyPackage` was created.

    ```         
    $ cd MyPackage
    $ tree
    .
    ├── Project.toml
    └── src
        └── MyPackage.jl
    ```

3.  Let's add some deps and code to our package by editing `src/MyPackage.jl`

    ``` julia
    module MyPackage

    using Example: domath # added this dep

    fact() = println("FYI, 2 + 5 = $(domath(2))") # added this new feature

    export fact

    end 
    ```

4.  Let's test our new features! 🤞

    ``` julia
    (@v1.9) pkg> activate .
      Activating project at `C:\Users\cpaniagu\Documents\Reusable-code-Julia\MyPackage`
    julia> using MyPackage
    [ Info: Precompiling MyPackage [934d1629-71ee-47e4-906a-ddb3ea0dd61f]
    ERROR: LoadError: ArgumentError: Package MyPackage does not have Example in its dependencies:
    - You may have a partially installed environment. Try `Pkg.instantiate()`
      to ensure all packages in the environment are installed.
    - Or, if you have MyPackage checked out for development and have
      added Example as a dependency but haven't updated your primary
      environment's manifest file, try `Pkg.resolve()`.
    - Otherwise you may need to report an issue with MyPackage
    [More error feedback here]
    ```

    Although we added the `Example` package to our base Julia environment, we are under a new independent environment `MyPackage` that does not know about `Example`.
    
    ```julia
    (MyPackage) pkg> st
    Project MyPackage v0.1.0
    Status `C:\Users\cpaniagu\Documents\DSCoV-Reusable-Julia\MyPackage\Project.toml` (empty project)

    (MyPackage) pkg> 
    ```

    In the error message above Julia is suggesting that we have an undocumented/uninstalled/broken dependency. Here we just need to add it to our project. Let's do it! 
    ```julia
    (MyPackage) pkg> add Example
       Resolving package versions...
        Updating `C:\Users\cpaniagu\Documents\Reusable-code-Julia\MyPackage\Project.toml`
      [7876af07] + Example v0.5.3
        Updating `C:\Users\cpaniagu\Documents\Reusable-code-Julia\MyPackage\Manifest.toml`
      [7876af07] + Example v0.5.3
    Precompiling project...
      1 dependency successfully precompiled in 1 seconds. 1 already precompiled.
    ```
    ```julia
    (MyPackage) pkg> st # again seeing is believing
    Project MyPackage v0.1.0
    Status `C:\Users\cpaniagu\Documents\Reusable-code-Julia\MyPackage\Project.toml`
    [7876af07] Example v0.5.3
    ```

    Now that the `Example` dep is documented and compiled let's try testing our package again! 
    ```julia
    julia> using MyPackage

    julia> fact()
    FYI, 2 + 5 = 7

    julia>
    ```
Success! Our feature works and we are ready (sort of) to share our package with the world!

### Recommended Configuration

Before sharing your code with the world, especially larger code bases, it's a good idea to have our code conform to a standard style. There is tooling for this available and there are many associated benefits:

1. **Consistency**: It ensures that your code has a consistent style, which makes it easier to read and understand.

2. **Saves Time**: You don't have to spend time manually formatting your code or arguing about coding styles in code reviews (when working with other people).

3. **Prevents Bugs**: Some formatters can catch and fix minor errors, such as missing semicolons, unused variables, etc.

4. **Integration with IDEs**: Most modern IDEs support automatic formatting on save, which makes it effortless to keep your code well-formatted.

5. **Focus on Logic**: With automatic formatting, you can focus on the logic of your code, rather than its appearance.


Here is a suggested configuration for VS Code with the Julia extension.
1.  Add a `.JuliaFormatter.toml` file with the following 
    ```toml
    style = "blue"
    ```
    Read about the *blue style* [here](https://blue.readthedocs.io/en/latest/).

2.  Add a `.gitignore` file 
    ```
    .JuliaFormatter.toml
    ```
The `.gitignore` file will prevent the configuration file just created from getting *pushed* to our remote repository.

 
## Publish your package!
Use tooling within VS Code (Source Control panel) for the following or Git to place your project/package in a remote repository.

Make the project a git repository, commit changes, and push your project to a remote repo to share with the world!
  ```shell
  $ git init
  $ git add .
  $ git commit -m 'My commit message'
  $ git remote add origin https://github.com/MyUserName/MyRepo.git
  $ git push origin main
  ```

Now others can use your package!
```julia
(@v1.9) pkg> add https://github.com/cpaniaguam/MyPackage.git
     Cloning git-repo `https://github.com/cpaniaguam/MyPackage.git`
    Updating git-repo `https://github.com/cpaniaguam/MyPackage.git`
   Resolving package versions...
    Updating `C:\Users\cpaniagu\.julia\environments\v1.9\Project.toml`
  [e06b4af7] + MyPackage v0.1.0 `https://github.com/cpaniaguam/MyPackage.git#main`
    Updating `C:\Users\cpaniagu\.julia\environments\v1.9\Manifest.toml`
  [e06b4af7] + MyPackage v0.1.0 `https://github.com/cpaniaguam/MyPackage.git#main`
Precompiling project...
  1 dependency successfully precompiled in 5 seconds. 231 already precompiled. 1 skipped during auto due to previous errors.

julia> using MyPackage

julia> fact()
FYI, 2 + 5 = 7