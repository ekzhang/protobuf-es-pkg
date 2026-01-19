# onnx-buf

This is an NPM package containing a lightweight compiled version of [`onnx.proto3`](https://github.com/onnx/onnx/blob/main/onnx/onnx.proto3) for JavaScript using [`@bufbuild/protobuf`](https://github.com/bufbuild/protobuf-es).

It can be imported and run from Node.js and Web.

## Usage

```bash
npm i onnx-buf
```

```ts
import { create } from "@bufbuild/protobuf";
import {
  TypeProtoSchema,
  TypeProto_TensorSchema,
  TensorShapeProtoSchema,
  TensorShapeProto_DimensionSchema,
  TensorProto_DataType,
} from "onnx-buf";

const typeProto = create(TypeProtoSchema, {
  value: {
    case: "tensorType",
    value: create(TypeProto_TensorSchema, {
      elemType: TensorProto_DataType.FLOAT,
      shape: create(TensorShapeProtoSchema, {
        dim: [
          create(TensorShapeProto_DimensionSchema, {
            value: { case: "dimValue", value: BigInt(1) },
          }),
          create(TensorShapeProto_DimensionSchema, {
            value: { case: "dimValue", value: BigInt(3) },
          }),
          create(TensorShapeProto_DimensionSchema, {
            value: { case: "dimValue", value: BigInt(244) },
          }),
          create(TensorShapeProto_DimensionSchema, {
            value: { case: "dimValue", value: BigInt(244) },
          }),
        ],
      }),
    }),
  },
});

console.log(typeProto);
```

## Versioning

The version of this package tracks the `onnx` repository version, with an additional suffix for changes. For instance `v1.20.0-0` of this repository is `v1.20.0` of ONNX.
