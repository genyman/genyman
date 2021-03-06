# genyman cli tool

The cli tool is the main tool of `genyman`. 

## File argument

`genyman your-config.json`

This argument is used to use the given file as input for the code generator specified in that configuration file. The cli is responsible for downloading, installing and executing the genyman global tool.

### update option

`genyman your-config.json --update`

The `update` option will perform and update of the package first.

## New Command

`genyman new`

This generates a new code generator solution template.

`genyman new packageId`

Will generate a new configuration template for the given packageId. 
Note that you can use the fully qualified packageId, or just the last part of the packageId.
For example, if you packageId is `MyGreatCompany.Genyman.MyFirstGenerator` you can use `genyman new MyFirstGenerator`.

### json option

`genyman new --json`

The json file format is the default format for configuration files. This option is now available for future support of other formats such as xml and yaml.

### file option

`genyman new --file <YOUR_FILENAME>`

If not specified the default configuration file is created with the name `gm-genyman.json`. If you want to use another name you can use this option.

### update option

`genyman new --update`

The `update` option will perform and update of the package first.

## Deploy Command

`genyman deploy`

The deploy command will build your code generator tool, pack it to a nupkg file and then push it to the specified, or default Nuget source.

### source option

`genyman deploy --source <YOUR_NUGET_SOURCE_URL>`

If you want to deploy to a private or local Nuget source, you can specify it with the source option.

### apikey option

`genyman deploy --apikey <YOUR_API_KEY>`

When you deploy to a Nuget source that needs an API key to publish, you need to specificy this option.

### major, minor, build option

`genyman deploy --major`

Before deployment using these options you can automatically increase a part of the version. If not specified `--build` is added by default.

## All Command

`genyman all`

Will scan the current folder for all `genyman` configuration files and will execute them all.

### recursive option

`genyman all --recursive`

The `recursive` option will scan not only the current folder, but all subfolders as well.

### update option

`genyman all --update`

The `update` option will perform and update of the packages first.

## Doc Command

`genyman doc`

or

`genyman doc packageId`

will print all properties and classes of the configuration of the generator.

### md option

You can even create a Markdown file if you specify a file name together with this option:

`genyman doc --md README.md`


## Generic Options

Following options are available for all commands.

### overwrite

`--overwrite`

All commands that generates files, will be able to overwrite existing files when this option is added. Otherwise a warning will be displayed.

### diagnostic

`--diagnostic`

This will show you all the Debug log lines together with the regular Info, Warning, Error and Fatal log lines.

### quiet

`--quiet`

If you don't want a single log line to appear in the console, you can use this option.