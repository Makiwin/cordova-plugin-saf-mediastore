# cordova-plugin-saf-mediastore

## Read and save files using the Storage Access Framework and Mediastore

This plugin allows you to read and save files using the Storage Access Framework and Mediastore on Android only.

## Available methods

```typescript
selectFolder(uri:string):Promise<string>
```
Launches an Intent to select a folder to which files can be saved. Returns the content URI.

```typescript
selectFile(uri:string):Promise<string>
```
Launches an Intent to select a file. Returns the content URI.

```typescript
openFolder(uri:string):Promise<void>
```
Launches an Intent to open a folder in the folder picker.

```typescript
openFile(uri:string):Promise<void>
```
Launches an Intent to open a file.

```typescript
readFile(uri:string):Promise<ArrayBuffer>
```
Reads a file as an ArrayBuffer.

```typescript
writeFile(params:{
	data:string,
	filename:string,
	folder?:string,
	subfolder?:string
}):Promise<string>
```
Writes a file to a specific filename, with the folder and subfolder being optional. The subfolder will be created if it does not exist, and the default folder is the Downloads folder (saved via Mediastore). Returns the content URI. ```data``` is a Base 64 string.

```typescript
saveFile(params:{
	data:string,
	filename?:string,
	folder?:string
}):Promise<string>
```
Launches a file picker Intent to save a file, with the preferred filename and folder being optional. Returns the content URI. ```data``` is a Base 64 string.

To call methods:
```
cordova.plugins.safMediastore.<function>(params); //returns a Promise
await cordova.plugins.safMediastore.<function>(params); //in an async function