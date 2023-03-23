## ParticipatoryProcess

```
name: Text
steps: Step[]
budget: Budget
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
author: Person/Organization
title: Text
dsescription: Text
cost: Number/Price
Scope: Text
ancestors: Proposal[]
successors: Proposal[]
currentStep: Step
activities: Activity[]
```
