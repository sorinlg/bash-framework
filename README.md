# bash-framework
Provides a shared code base for simple Bash scripts

## Usage

###  Step 0. Set the framework version that you want to use
```
_FRAMEWORK_VERSION='0.1.0'
```

###  Step 1. Add the framework repository as a submodule in your bash script project/repo
```
cd my_bash_project
git submodule add git@git.corp.adobe.com:aemm-sre-tools/bash-framework.git vendor/bash-framework    # get source code
git commit 'imported aemm-sre-tools/bash-framework as a submodule'                                  # save submodule reference to top-level repo
```

###  Step 2. Pin the desired version
```
cd vendor/bash-framework
git checkout ${_FRAMEWORK_VERSION}
cd -
git commit "fixed bash framework version @ ${_FRAMEWORK_VERSION}"
```

###  Step 3. Import framework into your code
```
### Framework boilerplate
###############################################################################
# calculate script root dir
ROOT_DIR="$( dirname $(realpath ${BASH_SOURCE[0]}) )"

# import bash framework
source "${ROOT_DIR}/../vendor/bash-framework/lib/import.sh"
```
