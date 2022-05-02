# Tour of F#

This is intended to be an overview of the F# language in small, incremental units. This work draws inspiration from the work of the Golang team and their Tour of Go (https://go.dev/tour/welcome/1)

### Pre-requisites

  * Dotnet SDK
  * Jupyter Lab (or Notebook)
      * Check if `pip` is installed: `pip --version`
      * If not present, install [Python](https://www.python.org/), which should install `pip`. If not,
        you can download [get-pip.py](https://bootstrap.pypa.io/get-pip.py) and run `python get-pip.py`.
      * Install Cargo from Rust required for Jupyter. 
         * For Windows, [download `rust-init.exe`](https://win.rustup.rs/x86_64) and run it, then follow onscreen instructions.
         * On *nix based systems, execute 
         
               curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

      * To confirm (on Windows) that `Cargo` is on your path, simply run `cargo --version`
      * `pip install jupyterlab` or `pip install notebook`
         * If you get errors on Windows during installation, it may be that your path defaults to a 32 bit installation of Python, 
           which [is not supported](https://github.com/spyder-ide/pywinpty/issues/129). To ensure you are running the right
           bitness version of Python you can run this command in a `cmd` window on Windows: 
           
               python -c "import sys;print(\"%x\" % sys.maxsize, sys.maxsize > 2**32)"

         * Another reason for errors on Windows is that Python, by default, does not uninstall earlier versions, which may
           linger on your `PATH`. Just manually uninstall older versions and ensure Python 64 bit, 3.8 or higher is installed.
                      
      * or install Anaconda which includes Jupyter
  * Dotnet interactive tool and .NET Jupyter kernels
      * https://github.com/dotnet/interactive/blob/main/docs/NotebookswithJupyter.md

