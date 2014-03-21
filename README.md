# AMML Spec Proposal

Semantic Assessment Model & Assessment Model Markup Language

## Objective

Create a standardized and universal model for testing items to unify teachers in the creation, proctor, and assessment of tests and the like. This standardized model will make assessment items portable, flexible, and sustainable for the digital world.

# How

SAM is a model (outlined in UML). The new syntax will provide educators with a standard and reliable way to capture a block of questions and answers, and produce a valid assessment item for testing.

The Assessment Model Markup Language (AMML) is an XML based model description language that aims to provide a common data format for defining and exchanging assessment data.

# The Model

## Types of assessments used in testing and polling

-   True/False
-   Multiple Choice
-   Multiple Correct
-   Fill-in/Initial Answer
-   Math
-   Matching
-   Ordering
-   Non-gradable:
  -   Essay
  -   Short Answer

# Objects

-   RootType
-   GroupType
-   ReferenceType
-   BlockType
-   DetailType

# Vocabulary

AMML contains a very spartan set of markup instructions (or tags) to encapsulate assessment data and metadata. The tags and attributes themselves are verbose and designed to be semantically self-defining.

## Global Attributes

-   `class`
-   `id`
-   `subject`
-   `lang`
-   `name/title`

## The Document Tag
`<Document>` - Every valid AMML document must be contained in these tags. A document is a collection of assessments and block groups.

## Blocks

An assessment block represents a single prompt. Each of the different tags represent different types of prompt. Each prompt has it’s own pattern to describe it, as well as metadata to modify it.

-   `<MultipleChoice>`
-   `<MultipleCorrect>`
-   `<Equation>`
-   `<TrueFalse>`
  -   `truelabel` - Defines the name of the “true” option.
  -   `falselabel` - Defines the name of the “false” option.
-   `<Matching>`
-   `<Ordering>`
-   `<FillIn>` - Fill in the blank.
  -   casesensitive: (true|false)
-   `<WriteIn>`
-   `<Generic>`

## Details
-   `<Prompt>`
-   `<Correct>`
-   `<Choice>`
-   `<Match>`
-   `<Explanation>`
-   `<ScratchSpace />`

## Assessment Template
`<Assessment>` represents an assessment template.

## Groups
`<Group>` - Represents a group of assessment blocks.

## Referencing Blocks and Groups
`<Use />` is a reference to a block or group that has already been defined.
  -   `href`

# Goals

1.  Establish a new standard for educators to rely on when developing,
    archiving, and distributing assessment items.
2.  Create a set of tools to make it easier.
3.  Create a public repository to facilitate goal \#1
4.  Registration as an official Media Type with the IANA:
    [http://www.iana.org/form/media-types](http://www.iana.org/form/media-types)

# Copyright and License

&copy; 2014 Gowon Patterson, Gowon Designs Ltd. Co. AMML is licensed under GPL V3. This document is released under the Creative Commons license.
