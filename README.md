# CakeContrib.Guidelines

[![standard-readme compliant][]][standard-readme]
[![All Contributors](https://img.shields.io/badge/all_contributors-0-orange.svg?style=flat-square)](#contributors)
[![Appveyor build][appveyorimage]][appveyor]
[![NuGet package][nugetimage]][nuget]

> Adds the cake-contrib default logo to the project

## Table of Contents

- [Install](#install)
- [Guidelines](#guidelines)
  - [Icon](#icon)
- [Maintainer](#maintainer)
- [Contributing](#contributing)
  - [Contributors](#contributors)
- [License](#license)

## Install

use one of the following:
```ps1
Install-Package CakeContrib.Guidelines
dotnet add package CakeContrib.Guidelines
paket add CakeContrib.Guidelines

```

or add the `PackageReference` manually
```
<PackageReference Include="CakeContrib.Guidelines" Version="0.1.0" />
```

See [NuGet](https://www.nuget.org/packages/CakeContrib.Guidelines/) for the current version.

## Guidelines

### Icon

Using this package with no special settings at all (i.e. "The Standard"):
* the current icon will be copied as "icon.png" in the project-directory
* the icon will be included in the project

#### Customizings

##### Icon-Location
The default location of the icon is `icon.png`, next to the csproj (i.e. `$(MSBuildProjectDirectory)/icon.png`).

Setting `CakeContribGuidelinesIconDestinationLocation` makes it possible to override the default location of the Icon. For example setting 

```xml
<PropertyGroup>
    <IconDestinationLocation>../logo.png</IconDestinationLocation>
</PropertyGroup>
```

in the csproj will place the icon as `logo.png` one folder up (relative to the current project).

##### Icon include in project
The icon will be automatically included in the project, unless `CakeContribGuidelinesIconOmitImport` was defined.

To to use a "custom" import the following could be used:

```
<PropertyGroup>
    <CakeContribGuidelinesIconOmitImport>1</CakeContribGuidelinesIconOmitImport>
</PropertyGroup>
<ItemGroup>
    <None Include="$(CakeContribGuidelinesIconDestinationLocation)">
        <Pack>True</Pack>
        <PackagePath></PackagePath>
    </None>
</ItemGroup> 
```

#### migrating from an existing project

* remove the existing icon
* remove the `Include` of the icon from the project-file
* add a reference to CakeContrib.Guidelines
* build the project
* set `PackageIcon` to `icon.png`

## Maintainer

[Nils Andresen @nils-a][maintainer]

## Contributing

CakeContrib.Guidelines follows the [Contributor Covenant][contrib-covenant] Code of Conduct.

We accept Pull Requests.
Please see [the contributing file][contributing] for how to contribute to CakeContrib.Guidelines.

Small note: If editing the Readme, please conform to the [standard-readme][] specification.

This project follows the [all-contributors][] specification. Contributions of any kind welcome!

### Contributors

Thanks goes to these wonderful people ([emoji key][emoji-key]):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

## License

[MIT License © Nils Andresen][license]

[all-contributors]: https://github.com/all-contributors/all-contributors
[appveyor]: https://ci.appveyor.com/project/nilsa/cake-cake-contrib-icon
[appveyorimage]: https://img.shields.io/appveyor/ci/nilsa/cake-cake-contrib-icon.svg?logo=appveyor&style=flat-square
[contrib-covenant]: https://www.contributor-covenant.org/version/1/4/code-of-conduct
[contributing]: CONTRIBUTING.md
[emoji-key]: https://allcontributors.org/docs/en/emoji-key
[maintainer]: https://github.com/nils-a
[nuget]: https://nuget.org/packages/CakeContrib.Guidelines
[nugetimage]: https://img.shields.io/nuget/v/CakeContrib.Guidelines.svg?logo=nuget&style=flat-square
[license]: LICENSE.txt
[standard-readme]: https://github.com/RichardLitt/standard-readme
[standard-readme compliant]: https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square