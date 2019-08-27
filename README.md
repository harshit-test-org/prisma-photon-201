# Introduction

Reproduction for https://github.com/prisma/photonjs/issues/201

# To Reproduce

1. Clone and run `prisma2 dev`
2. Open `src/script.ts` and try using `bars` in the create object as a key. It is unavailable in the type defs
3. Now open `prisma/schema.prisma` and change the `Bar` model to the following:

```groovy
model Bar {
  id               ID
  otherFooVersions FooVersion[] @relation("B")
}
```

4. The `bars` property is now accessible in the create input.
