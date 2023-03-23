## ParticipatorySpace

```
since: Date
owner: AdministrativeArea
schedule: Schedule
cumulativeBudget: MonetaryAmount
```


## ParticipatoryProcess

```
name: Text
description: Text
definition: Step[]
budget: MonetaryAmount
start: Date
end: Date
currentStep: Step
participatorySpace: ParticipatorySpace
```

## Step

```
name: Text
start: Date
end: Date
constraints: Text
possibleActivities: Activity[]
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
activities: Activity[]
```

## Activity (enumeration)

```
Submission
Retraction
Amendment
Merge
Split
Cancellation
VoteAccepting
VoteRejecting
ImplementationSuccessful
ImplementationPartlySuccessful
ImplementationUnsuccessful
```
