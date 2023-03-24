---
title: ontologies
description: linked-data schema
date: 2023-03-23
---
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Participatory Processes - schema draft](#participatory-processes---schema-draft)
  - [TranslatedThing](#translatedthing)
  - [ParticipatorySpace](#participatoryspace)
  - [ParticipatoryProcess < TranslatedThing](#participatoryprocess--translatedthing)
  - [Step < TranslatedThing](#step--translatedthing)
  - [Proposal < TranslatedThing](#proposal--translatedthing)
  - [VoteAction < Action](#voteaction--action)
  - [DelegateVoteAction < Action](#delegatevoteaction--action)
  - [FollowAction < Action](#followaction--action)
  - [CommentAction < Action](#commentaction--action)
  - [ShareAction < Action](#shareaction--action)
  - [Activity](#activity)
    - [ActivityVerb](#activityverb)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->
# Participatory Processes - schema draft

![High-level view](/images/schema.png)
## TranslatedThing
```
inLanguage: Language | Text
availableLanguages: Language[] | Text
machineTranslated: Boolean
```

## ParticipatorySpace

```
identifier: PropertyValue | Text | URL
since: Date
owner: AdministrativeArea
schedule: Schedule
cumulativeBudget: MonetaryAmount
```

## ParticipatoryProcess < TranslatedThing

```
identifier: PropertyValue | Text | URL
name: Text
description: Text
topics: DefinedTerm[]
definition: Step[]
budget: MonetaryAmount
start: Date
end: Date
currentStep: Step
participatorySpace: ParticipatorySpace
availableAction: FollowAction
```

## Step < TranslatedThing

```
identifier: PropertyValue | Text | URL
name: Text
start: Date
end: Date
constraints: Text
possibleActivities: Activity[]
```

## Proposal < TranslatedThing

```
identifier: PropertyValue | Text | URL
author: Person | Organization
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
history: Activity[]
availableActions: Action[]
```

## VoteAction < Action
```
voteType: Text 
```

## DelegateVoteAction < Action
```
availableRepresentants: Person[] | Organization[]
```

## FollowAction < Action

## CommentAction < Action

## ShareAction < Action

---

## Activity
```
identifier: PropertyValue | Text | URL
actor: Person | Organization
do: ActivityVerb
actsOn: Thing
at: DateTime
```

### ActivityVerb

```
Submit
Retract
Amend
Merge
Split
Cancel
ChangeBudget
VoteInFavour
VoteAgainst
StartImplementation
ImplementSuccessfully
ImplementPartlySuccessfully
ImplementUnsuccessfully
AbortImplementation
```