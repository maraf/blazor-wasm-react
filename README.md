# Blazor WASM in a react application

This sample shows how to use Blazor WebAssembly integrated into a React application.

## Project structure

- **app**: target react application using rollup to do the JavaScript build
- **blazor**: Blazor WebAssembly application containing several components

## Live demo

https://maraf.github.io/blazor-wasm-react/

## Building source code

### Blazor components

- Install .NET 10 SDK (preview7+)
- Run `dotnet publish` in the `blazor` folder

### App

In the `react` folder

- Run `npm install`
- Run `npm run build`

### Under the hood

In .NET 10 we have added a way to produce JavaScript bundler friendly build output. In JavaScript world, file dependencies (like other JS files or images) are resolved using import statements.
In browser world, only JavaScript files can be imported using import statements. Because of this, we introduced an MSBuild property `WasmBundlerFriendlyBootConfig=true` to switch between browser-runnable output 
and JavaScript bundler-friendly build output. Switching this on allows JavaScript bundlers to consume output of .NET build (publish).
