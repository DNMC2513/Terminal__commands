# Pip to manage dependencies
```Dependencies are also called libraries or modules. The name is based on the fact that certain libraries and modules rely on others to function properly. ```

## Outline
1. pip to install:
- a single dependency
- a batch of dependencies

2. pip to check the current list of installed dependencies:
- check the name and version of each dependency
- check the outdated dependencies
- check the updated dependencies
- chek whether the dependencies that others are reliant on are there

3. pip to uninstall:
- a single dependency
- a batch of dependencies

  4. pip to upgrade:
  - a single dependency
  - all outdated dependencies

`TIPS`:
- Cancel the process of a command
- Check the manual of pip

## 1. pip to install:
### a. a single dependency:
```bash
pip install [dep_name]
```
### b. a batch of dependencies within a source code:
```bash
pip install -r requirement.txt
```

## 2. pip to check the current list of installed dependencies:
### a. check the name and the version of each dependency:
```bash
pip freeze

#or use this cmd for a better format:
pip list
```
### b. check the list of outdated dependencies:
```bash
pip list -o
```

### c. check the list of outdated dependencies:
```bash
pip list -u
```

### d. chek whether the dependencies that others are reliant on are there:
```bash
pip chek
```

## 3. pip to unistall:
### a. a single dependency:
```bash
pip unistall [dep_name]
```

### b. a batch of dependencies:
```bash
pip unintall -r req.txt
```

## 4. pip to upgrade:
### a. single dependency:
```bash
pip install [dep_name] --upgrade
```

### b. All outdated dependecies:
```bash
#assign the list of dependencies into a text file:
pip freeze > y.txt

#replace all the symbol == with <=:
(Get-Content [file_dir] ) -Replace '==',''>=' | Set-Content [file_dir]

# UPGRADE the batch:
pip install -r y.txt --upgrade

```

## `TIPS`:
- Cancel the process of a command or to exist from the terminal:
`CTRL + Z`
- Check the MANUAL of pip:
```bash
pip --help
```


 

