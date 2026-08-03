# ModFlow 6 and Flopy Notes

Link : [Australian Water School](https://youtu.be/xDgWjArrHNY?si=HZ1m6bbJjCIL4huV)

```python
Columns 
0 ->
Rows
0
|
V
```

![alt text](image.png)

```python
# delr: increases from West to East
# delr: 0 ->

# delc: increases from North to South
# delc: 0
#       |
#       V
```

### use consistent units
Water in Postive
Water out Negative

Distance: Meters
Time: Days




## Modflow Examples Links

[modflow examples github](https://github.com/MODFLOW-ORG/modflow6-examples/tree/master)

[modflow binary executables](https://github.com/MODFLOW-ORG/modflow6-nightly-build/releases)

## package manager used by USGS
[Pixi](https://pixi.prefix.dev/latest/installation/)

Installation for Linux
```bash
curl -fsSL https://pixi.sh/install.sh | sh
```


### First step 
Check if pixi is installed properly 
```bash
pixi --version
```
Check if the project is recognized by pixi within the same directory

```bash
pixi info
```

Followed by the installation of the environmental

```bash
pixi install
```

Example of what you should see 

```bash
jorge@jorge:~/Documents/modflow6-examples$ pixi info
System
------------
       Pixi version: 0.75.0
        TLS backend: rustls
           Platform: linux-64
   Virtual packages: __unix=0=0
                   : __linux=6.17.0=0
                   : __glibc=2.39=0
                   : __cuda=13.2=0
                   : __archspec=1=skylake
          Cache dir: /home/jorge/.cache/rattler/cache
       Auth storage: /home/jorge/.rattler/credentials.json
   Config locations: No config files found

Global
------------
            Bin dir: /home/jorge/.pixi/bin
    Environment dir: /home/jorge/.pixi/envs
       Manifest dir: /home/jorge/.pixi/manifests/pixi-global.toml

Workspace
------------
               Name: modflow6-examples
            Version: 1.0.0
      Manifest file: /home/jorge/Documents/modflow6-examples/pixi.toml
       Last updated: 01-08-2026 23:35:48

Environments
------------
        Environment: default
           Features: default
           Channels: conda-forge, nodefaults
   Dependency count: 34
       Dependencies: python, boltons, appdirs, cffconvert, codespell, filelock, flaky, fprettify, fortran-language-server, gitpython, geopandas, jinja2, jupytext, matplotlib, meson, ninja, numpy, pip, pooch, pyshp, pytest, pytest-benchmark, pytest-dotenv, pytest-order, pytest-xdist, pyvista, rasterio, rasterstats, ruff, scipy, shapely, syrupy, tomli, tomli-w
  PyPI Dependencies: flopy, mfpymake, modflowapi, modflow-devtools, sphinx-markdown-tables, nbsphinx-link, rtds-action, nbconvert, nbsphinx, ipython, ipykernel, sphinx-rtd-theme, pygments, myst-parser
   Target platforms: win-64, linux-64, linux-aarch64, osx-arm64, osx-64
   Minimum platform: available after `pixi install`
    Prefix location: /home/jorge/Documents/modflow6-examples/.pixi/envs/default
              Tasks: fix-format, install, scripts, check-spelling, build-plots, build-latex-md, jupytext, notebooks, script, jupyter, make-pdf, build-pdflatex, fix-spelling, build-rst, make-rtd, notebook, build-sphinx, update-flopy, build-input, check-format, update-environment-yml

jorge@jorge:~/Documents/modflow6-examples$ pixi install
 WARN the lock file is up-to-date but uses an older format (v6), run `pixi lock` to upgrade to v7 for improved reproducibility
▪ preparing packages   [━━━━━━━━━━━━━━━━━━━━] 283/283    ▪ installing           [━━━━━━━━━━━━━━━━━━━━] 283/283    ⠴ updating pypi packages in 'default'                      ⠒ Preparing distributi [00:01:01] [━━━━━━━━━━━━━━━━━━━━]   63/64                                        ```



```bash
cd scripts
pixi run get-modflow .
```


# Goal handwrite the following tutorial example

[flopy Tutorial](https://youtu.be/xDgWjArrHNY?si=qMP7sW7MTDzzvqlp)

setup the environment
document how you did that 
write everything by hand
run it 
modify it
and then go back to reviewing flopy example repo

go back up to line 45
