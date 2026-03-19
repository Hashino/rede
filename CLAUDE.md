# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

`rede` (Portuguese for "network") is a decentralized alternative to Git/GitHub/GitHub Pages. It is currently in the **conceptual/planning phase** with no implementation yet.

### Core Concept

- Every user is both a client and a server, running the network code and distributing stored files
- Resource contribution (storage/processing) proportionally grants storage/processing usage rights and voting power
- The network is hierarchical: sub-networks run their own code on top of the parent network's code
- New users can only join when there is available capacity
- Sub-networks contributing >1% of parent resources can vote to add code to the parent (2/3 majority required)
- Sub-networks contributing >10% of parent resources can vote to replace parent code (2/3 majority required)
- The root network provides storage/hosting with a JIT compiler to run the network code

## Current State

No build system, no source code, no tests — this repository contains only documentation. The first task when implementation begins will be to choose a language/stack and set up the project scaffold.
