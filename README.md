// For format details, see https://aka.ms/devcontainer.json. For config options, see the README at:
// https://github.com/microsoft/vscode-dev-containers/tree/v0.177.0/containers/javascript-node
// -
{
	"name": "docs.github.com",
	"build": {
		"dockerfile": "Dockerfile",
		// Update 'VARIANT' to pick a Node version: 12, 14, 16
		"args": { "VARIANT": "16" }
	},

	// Set *default* container specific settings.json values on container create.
	"settings": {
		"terminal.integrated.shell.linux": "/bin/bash",
		"cSpell.language": ",en"
	},

	// Install features. Type 'feature' in the VS Code command palette for a full list.
	"features": {
		"git-lfs": "latest",
		"sshd": "latest"
	 },

	// Visual Studio Code extensions which help authoring for docs.github.com.
	"extensions": [
		"dbaeumer.vscode-eslint",
		"sissel.shopify-liquid",
		"davidanson.vscode-markdownlint",
		"bierner.markdown-preview-github-styles",
		"streetsidesoftware.code-spell-checker",
		"alistairchristie.open-reusables"
	],

	// Use 'forwardPorts' to make a list of ports inside the container available locally.
	"forwardPorts": [4000],

	// Use 'postCreateCommand' to run commands after the container is created.
	"postCreateCommand": "git lfs pull && npm ci",

	// Comment out connect as root instead. More info: https://aka.ms/vscode-remote/containers/non-root.
	"remoteUser": "node"
,
	"hostRequirements": {
		"memory": "8gb"
	 }
}
