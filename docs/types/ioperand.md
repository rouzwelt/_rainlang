[Home](../index.md) &gt; [IOperand](./ioperand.md)

# Type IOperand


<b>Signature:</b>

```typescript
type IOperand = {
    isZeroOperand: boolean;
    argsRules: OperandArgRange[];
    encoder: (_args: number[], _paramsLength: number) => number;
    decoder: (_operand: number) => number[];
};
```
