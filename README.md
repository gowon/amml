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

---

# Item Types

-   RootType
-   GroupType
-   ReferenceType
-   BlockType
-   DetailType

# Vocabulary

AMML contains a very spartan set of markup instructions (or elements) to encapsulate assessment data and metadata. The tags and attributes themselves are verbose and designed to be semantically self-defining.

## Global Attributes

-   `class`
-   `id`
-   `lang`
-   `name`
-   `title`

## The Document Element
`<Document>` - Every valid AMML document must be contained in these tags. A document is a collection of assessments and groups, and can optionally contain metadata to describe the doctument.

## Meta Elements
`<Meta />` elements can be used to describe the document. Each Meta element represens a single piece of information. There is no bound to how many Meta elements can be used in a document.

### Meta Attributes
- `name`
- `content`

### Examples
```
<Meta name="author" content="Gowon Patterson" />
<Meta name="last-updated" content="[RFC 2822 format date]" />
```

## Block Elements

An block element represents a single prompt. Each of the different elements represent an explicit type of prompt. Each prompt has it’s own pattern to describe it, as well as metadata to modify it. All of the elements are based off the `<Generic>` block element, which can be used in lieu of an explicit type.

### Generic Block Attributes
- [Global attributes](#)
- `subject`

### Semantic Block Elements
-   `<MultipleChoice>`
-   `<MultipleCorrect>`
-   `<Equation>` (use with LaTeX)
-   `<TrueFalse>`
  -   `truelabel` - Defines the name of the “true” option.
  -   `falselabel` - Defines the name of the “false” option.
-   `<Matching>`
-   `<Ordering>`
-   `<FillIn>` - Fill in the blank.
  -   `casesensitive` (true|false)
-   `<WriteIn>`

## Detail Elements
-   `<Prompt>`
-   `<Correct>`
-   `<Choice>`
-   `<Match>`
-   `<Explanation>`
-   `<ScratchSpace />`

## Assessment Element
`<Assessment>` represents an assessment template.

## Group Element
`<Group>` - Represents a group of assessment blocks.

## Referencing Blocks and Groups
`<Use />` is a reference to a block or group that has already been defined, by id.
  -   `href`

# Goals

1.  Establish a new standard for educators to rely on when developing,
    archiving, and distributing assessment items.
2.  Create a set of tools to make it easier.
3.  Create a public repository to facilitate goal \#1
4.  Register (*.amml; application/amml+xml) as an official Media Type with the IANA:
    [http://www.iana.org/form/media-types](http://www.iana.org/form/media-types)

# Copyright and License

Copyright &copy; 2015 Gowon Patterson, Gowon Designs Ltd. Co. 

AMML is licensed under the terms of the [GNU General Public License Version 3][gpl-license].

This document is licensed under the terms of the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc4-license].

[gpl-license]: http://www.gnu.org/licenses/gpl-3.0.html
[cc4-license]: http://creativecommons.org/licenses/by-nc-sa/4.0/
