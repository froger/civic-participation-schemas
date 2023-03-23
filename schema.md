# Participatory Processes - schema

## Draft

![High-level view](schema.png)

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
topics: DefinedTerm[]
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
topics: DefinedTerm
affected: AdministrativeArea or Place
proposedBudget: MonetaryAmount
approvedBudget: MonetaryAmount
Scope: Text
participatoryProcess: ParticipatoryProcess
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
BudgetChange
VoteAccepting
VoteRejecting
ImplementationSuccessful
ImplementationPartlySuccessful
ImplementationUnsuccessful
ImplementationAborted
```
