# Post Academy Days: Pact JS workshop

## Introduction

This workshop is aimed at demonstrating core features and benefits of contract testing with Pact.

Whilst contract testing can be applied retrospectively to systems, we will follow the [consumer driven contracts](https://martinfowler.com/articles/consumerDrivenContracts.html) approach in this workshop - where a new consumer and provider are created in parallel to evolve a service over time, especially where there is some uncertainty with what is to be built.

This workshop should take from 1 to 2 hours, depending on how deep you want to go into each topic.

**Workshop outline**:

steps marked **INTERACTIVE** have coding elements for breakout rooms. solutions are in the corresponding `step{x}_5` branch.

1. Create our consumer before the Provider API even exists
1. Write a unit test for our consumer **INTERACTIVE**
1. Write a Pact test for our consumer **INTERACTIVE**
1. Verify the consumer pact with the Provider API
1. Fix the consumer's bad assumptions about the Provider
1. Write a pact test for `404` (missing User) in consumer **INTERACTIVE**
1. Update API to handle `404` case **INTERACTIVE**
1. Write a pact test for the `401` case **INTERACTIVE**
1. Update API to handle `401` case
1. Fix the provider to support the `401` case
1. Implement a broker workflow for integration with CI/CD
1. Implement a managed pactflow workflow for integration with CI/CD

_NOTE: Each step is tied to, and must be run within, a git branch, allowing you to progress through each stage incrementally. For example, to move to step 2 run the following: `git checkout step2`_

## Learning objectives

If running this as a team workshop format, you may want to take a look through the [learning objectives](./LEARNING.md).

## Requirements

[Docker](https://www.docker.com)

[Docker Compose](https://docs.docker.com/compose/install/)

[Node + NPM](https://nodejs.org/en/)

## Getting Started

Pull down all the branches in the remote repo:

```sh
git branch -r | grep -v '\->' | sed "s,\x1B\[[0-9;]*[a-zA-Z],,g" | while read remote; do git branch --track "${remote#origin/}" "$remote"; done
git fetch --all
git pull --all
npm install
```

Each branch is the end of the each step in the workshop.

## Scenario

There are two components in scope for our workshop.

1. Product Catalog website. It provides an interface to query the Product service for product information.
1. Product Service (Provider). Provides useful things about products, such as listing all products and getting the details of an individual product.

## Let's get started!

```sh
git checkout step1
```
