# **Rain Language**
A WIP Parser and Formatter written in TypeScript used to read and write in Rain Language.
The primary goal of the rain language is to make smart contract development accessible for as many people as possible.

This is fundamentally grounded in our belief that accessibility is the difference between theoretical and practical decentralisation. There are many people who would like to participate in authoring and auditing crypto code but currently cannot. When someone wants/needs to do something but cannot, then they delegate to someone who can, this is by definition centralisation.

For more info and details, please read this [article](https://hackmd.io/@REJeq0MuTUiqnjx9w5SsUA/HJj9s-nfi#Rainlang-has-a-spectrum-of-representations-from-concise-gtexplicit)

If you find an issue or you want to propose a better way to show a specific script or opcodes, pleasefeel to do it on: [issues](https://github.com/rouzwelt/rainlang/issues)
<br>

## **Tutorial**
To get started, install the package:
```bash
yarn add --dev https://github.com/rouzwelt/rainlang
or
npm install --save-dev https://github.com/rouzwelt/rainlang
```
<br>

### **Parser**
Parser is a compiler to generate a valid StateConfig (deployable bytes) from a text i.e. rain expressions.
```typescript
// to import
import { Parser } from "rain-sdk";

// to set the custom opmeta
Parser.set(opmeta);

// to set the custom details of GTE and LTE opcodes
Parser.setGteMeta(name?, description?, data?, description?);
Parser.setLteMeta(name?, description?, data?, description?);

// to execute the parsing and get parse tree object and StateConfig
let parseTree;
let stateConfig;
[ parseTree, stateConfig ] = Parser.get(textScript, customOpMeta, customMultiOutputPlaceholderChar);

// to get parse tree object only
let parseTree = Parser.getParseTree(textScript, customOpMeta, customMultiOutputPlaceholderChar);

// to get StateConfig only
let stateConfig = Parser.getStateConfig(textScript, customOpMeta, customMultiOutputPlaceholderChar);

// to build StateConfig (bytes) from ParseTree object or a Node or array of Node
let argument: Node || Node[] || ParseTree
let stateConfig = Parser.buildBytes(argument)
```
<br>

### **Formatter**
The generator of human friendly readable source.
Parse an StateConfig/Script to a more human readable form, making easier to understand. This form allows users read exactly
what the Script will do, like the conditions, values used, etc. Also, anyone can learn to write their own scripts
if use the Human Form to see the output for each combination that they made.
<br>

## **Developers**
To get started, clone the repo and install the dependencies:
```bash
git clone https://github.com/rouzwelt/rainlang
cd rainlang
yarn install
```
<br>

To build from source code:
```bash
yarn run build
```
<br>

To generate documents:
```bash
yar run docgen
```
<br>

To run tests:
```bash
yarn run test
```
