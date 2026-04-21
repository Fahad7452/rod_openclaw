# Purpose of EffectOS

## Mission

EffectOS exists to make computational effects governable by design.
The project separates reasoning from execution and enforces deterministic authorization before any state change occurs.

## Problem Statement

In traditional systems, runtime owns both:
- Decision-making logic
- Execution authority

That coupling creates a high-impact failure mode: if runtime is compromised, unauthorized effects may still execute.

## What EffectOS Changes

EffectOS moves execution authority into MEG (Machine-Enforced Governance):
- Runtime proposes actions
- MEG validates actions against explicit policy
- MEG executes only approved actions
- Every authorized execution is auditable

## Project Scope

EffectOS currently focuses on:
- Effect validation and authorization boundaries
- Deterministic execution flows for tools, APIs, and stateful operations
- Auditable effect trails for post-incident and compliance analysis
- SDK-driven integration for agent and application environments

## Non-Goals

EffectOS is not:
- A generic sandbox
- A replacement for identity systems like RBAC/ABAC
- A runtime hardening product

It is a governance-first compute model for effect execution.
