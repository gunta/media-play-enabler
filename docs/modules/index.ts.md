---
title: index.ts
nav_order: 1
parent: Modules
---

## index overview

media-play-enabler
Enables video play programmatically on modern browsers that require user input events

Added in v0.0.1

---

<h2 class="text-delta">Table of contents</h2>

- [utils](#utils)
  - [MediaPlayEnabler (class)](#mediaplayenabler-class)
    - [addSourceToVideo (method)](#addsourcetovideo-method)
    - [enablePlay (method)](#enableplay-method)
    - [create (method)](#create-method)
    - [canPlay (method)](#canplay-method)
    - [playCanBeUsed (property)](#playcanbeused-property)

---

# utils

## MediaPlayEnabler (class)

**Signature**

```ts
export declare class MediaPlayEnabler {
  constructor(options: IMediaPlayEnablerOptions)
}
```

Added in v0.0.1

### addSourceToVideo (method)

**Signature**

```ts
private addSourceToVideo(
    element: HTMLVideoElement /*, type: string, */,
    src: string,
  ): void
```

Added in v0.0.2

### enablePlay (method)

**Signature**

```ts
private enablePlay(): void
```

Added in v0.0.1

### create (method)

**Signature**

```ts
private create(): void
```

Added in v0.0.1

### canPlay (method)

**Signature**

```ts
public async canPlay(): Promise<boolean>
```

Added in v0.0.1

### playCanBeUsed (property)

**Signature**

```ts
playCanBeUsed: boolean
```

Added in v0.0.1
