# python 2&3 coexist on Mac

 _special version under special folder_

tool: **pyenv**

## Install

-  uninstall python2 and python3 if has exsited  
`which python2` -> get path of python2  
`which python3` -> get path of python3

- install pyenv:         ---------------------got  
`brew install pyenv`

- add pyenv to PATH by adding below code to ~/.zshrc file:    ---------------------got
 ```
    export PATH="$HOME/.pyenv/bin:$PATH"
    eval "$(pyenv init -)" 
 ```

- check if pyenv installed successfully:  
`pyenv --version`

- check the system environment    ---------------------got  
`brew doctor`

- pyenv suite installer:  
`curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | zsh`    ---------------------got  

- install/upgrade xcode    ---------------------got  
`xcode-select --install`

## Usage

- install python 3.7.0 by pyenv  
`pyenv install 3.7.0` 

- list versions of python installed by pyenv  
`pyenv versions`

- config specified version(3.7.0) under the special folder  
`cd _TARGET_FOLDER_`  
`pyenv local 3.7.0`


## Results  
```
➜  pyLearning python --version  
Python 3.7.0  
➜  pyLearning cd ..         
➜  ~ python --version  
Python 2.7.15  
```

## \* Errors encountered in the process:

1.   
    `pyenv install 3.7.0`  
__Error__: "zipimport.ZipImportError: can't decompress data; zlib not available"  
__Fixed__: `xcode-select --install`  

2. 
    ```
	➜  pyLearning pyenv global
	system
	➜  pyLearning pyenv local 
	3.7.0
	➜  pyLearning python --version
	Python 2.7.10
	➜  pyLearning cd ..
	➜  ~ python --version
	Python 2.7.10 #[restart terminal and this would fixed.]
	```


reference links:
- https://zhuanlan.zhihu.com/p/25990928
- https://github.com/pyenv/pyenv/issues/530
- https://amaral.northwestern.edu/resources/guides/pyenv-tutorial




