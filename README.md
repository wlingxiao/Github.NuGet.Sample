Example for publishing nuget package to GitHub registry.

#### Publish package
1. Generate personal access tokens (classic) including `repo` and `write:packages` permissions.
2. Add the GitHub package source to `NuGet` using the command below.
`dotnet nuget add source --username USERNAME --password TOKEN --store-password-in-clear-text --name github "https://nuget.pkg.github.com/NAMESPACE/index.json"`
Replace NAMESPACE with the name of the personal account, and TOKEN with your token obtained from step 1.
3. Package the project using `dotnet pack --configuration Release`.
4. Publish the package using `dotnet nuget push "bin/Release/PROJECT_NAME.1.0.0.nupkg"  --api-key TOKEN --source "github"`.
Replace PROJECT_NAME with the name of the project, and TOKEN with your token obtained from step 1.
