# Tour of F#

This is intended to be an overview of the F# language in small, incremental units. This work draws inspiration from the work of the Golang team and their Tour of Go (https://go.dev/tour/welcome/1)

### Pre-requisites

  * Dotnet SDK
  * Jupyter Lab (or Notebook)
      * Check if `pip` is installed: `pip --version`
      * If not present, install [Python](https://www.python.org/), which should install `pip`. 
      * If you have Python but not `pip`, you can download [get-pip.py](https://bootstrap.pypa.io/get-pip.py) 
        and run `python get-pip.py` to install it.
      * Install [Cargo](https://doc.rust-lang.org/cargo/) from Rust required for Jupyter. 
         * For Windows, [download `rust-init.exe`](https://win.rustup.rs/x86_64) and run it, then follow onscreen instructions. 
           This will also install Cargo.
         * On *nix based systems, execute 
         
               curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

      * To confirm that `Cargo` is installed and your path, simply run `cargo --version`
      * Run `pip install jupyterlab` (which includes Notebook) or `pip install notebook` (just Notebook)
         * If you get errors on Windows during installation, it may be that your path defaults to a 32 bit installation of Python, 
           which [is not supported](https://github.com/spyder-ide/pywinpty/issues/129). To ensure you are running the right
           bitness version of Python you can run this command in a `cmd` window on Windows: 
           
               $ python -c "import sys;print(\"%x\" % sys.maxsize, sys.maxsize > 2**32)"
               7fffffffffffffff True       # this means it's 64 bit

         * Another reason for errors on Windows is that Python, by default, does not uninstall earlier versions, which may
           linger on your `PATH`. Just manually uninstall older versions from _Apps & Features_ and ensure Python 64 bit, 
           3.8 or higher is installed: `python --version`.
+
      * Or [install Anaconda](https://docs.anaconda.com/anaconda/install/index.html) which includes Jupyter

  * Dotnet interactive tool and .NET Jupyter kernels
      * Summary of [these instructions](https://github.com/dotnet/interactive/blob/main/docs/NotebookswithJupyter.md):
      * Ensure your .NET version is 6.x: `dotnet --version`
      * Ensure Jupyter has Python 3: `jupyter kernelspec list` and not yet Dotnet Interactive
      * In a command prompt, install Dotnet Interactive: `dotnet tool install -g Microsoft.dotnet-interactive`
      * From command prompt, or an Anaconda prompt, run: `dotnet interactive jupyter install`
         * This is installs the .NET C#, F# and PowerShell interactive kernels
      * Now running `jupyter kernelspec list` gives you:

            Available kernels:
            .net-csharp        C:\Users\...\Roaming\jupyter\kernels\.net-csharp
            .net-fsharp        C:\Users\...\Roaming\jupyter\kernels\.net-fsharp
            .net-powershell    C:\Users\...\Roaming\jupyter\kernels\.net-powershell
            python3            C:\Users\...\Local\Programs\Python\Python310\share\jupyter\kernels\python3

      * If you just need to update this, run:

            dotnet tool update -g Microsoft.dotnet-interactive

  * Now you can run:
      * `jupyter lab`, which starts the JupyterLab, if you installed that
      * `jupyter notebook`, which starts the Jupyter Notebook
      * this should open your browser, for instance to `http://localhost:8888/tree`, where you can browse and 
        interactively edit and run your code.

        For instance, navigate to `Tour_of_F%23_Part1.ipynb` and click to open it and edit it.
