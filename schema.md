## ParticipatoryProcess

```
name: Text
steps: Step[]
budget: MonetaryAmount
start: Date
end: Date
```

## Step

```
start: Date
end: Date
constraints: Text
name: Text
```

## Proposal

```
author: Person or Organization
title: Text
description: Text
cost: MonetaryAmount
Scope: Text
ancestors: Proposal[]
successors: Proposal[]
currentStep: Step
activities: Activity[]
```

## Activity

```
tbd.
```
