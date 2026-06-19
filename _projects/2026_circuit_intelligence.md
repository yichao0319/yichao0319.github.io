---
layout: project
title: Circuit Intelligence -- LMM for PCB Design
description: A long-term research and translation direction for LMM-powered PCB design. We build multimodal PCB data, circuit-specific reasoning agents, and design-to-manufacturing validation loops that transform requirements, datasheets, IC footprints, schematics, layouts, BOMs, Gerbers, and production rules into structured, verifiable design assets.
img: assets/img/projects/project-circuit-intelligence-cover-gpt.png
importance: 2026
category: research
date: 2026-06-17
show: true

authors:
  - name: Yida Wang
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University and collaborators
  - name: Taiting Lu
    url: ""
    affiliations:
      name: Penn State University
  - name: Yi-Chao Chen
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University and collaborators
  - name: Mahanth Gowda
    url: ""
    affiliations:
      name: Penn State University

---

## Overview

PCB design is still a high-friction engineering workflow. A designer must translate product requirements into functional modules, search datasheets, choose ICs, create footprints, draw schematics, reason about nets, verify rules, simulate behavior, prepare layouts, and finally package BOM, Gerber, assembly, and 3D files for manufacturing. Small mistakes in pin geometry, connectivity, or design rules can trigger expensive respins.

Circuit Intelligence is our vision for **LMM for PCB Design**: a domain-specific multimodal system that understands circuit artifacts as engineering documents, not ordinary pictures. The goal is to place natural language requirements, datasheets, package drawings, PCB schematics, layouts, BOMs, Gerbers, and production constraints into a shared semantic space where models and agents can reason, check, and generate verifiable design assets.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-cover-gpt.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1  Circuit Intelligence links IC footprint geometry, LMM-based reasoning, and PCB schematic understanding into a broader LMM4PCB design workflow.
</div>

## LMM4PCB Vision

The LMM4PCB direction asks how a model can move from "reading" circuit diagrams to participating in an engineering workflow. A useful PCB model must parse requirements, retrieve device knowledge, understand geometry, recover schematic topology, reason about constraints, and expose uncertainty before its output enters an EDA or manufacturing flow.

Our work treats the platform as a closed loop rather than a single prediction task. Multimodal data and PCB knowledge bases provide the domain substrate. Specialized agents handle requirement parsing, footprint geometry, schematic graph reasoning, rule review, and EDA interaction. Structured outputs then return to simulation, prototype verification, and manufacturing feedback.

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-lmm4-prediction.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2  Paper example of footprint-geometry reasoning: circuit artifacts must be converted from visual diagrams into structured pin counts, coordinates, and dimensions.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-lmm4-land-pattern.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3  Footprint drawings encode package geometry, pad placement, pitch, and layout constraints that must become machine-readable design data.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-lmm4-sample.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4  Multimodal circuit data links real datasheet diagrams with structured question-answer style geometry annotations.
</div>

## Technical Stack

**Engineering semantic layer.** PCB artifacts are heterogeneous: text requirements, datasheet tables, package diagrams, schematic symbols, spatial layouts, BOM rows, and manufacturing rules. We organize them as linked multimodal objects so that models can reason over geometry, topology, text, and constraints together.

**Agentic design workflow.** The system decomposes PCB work into auditable steps: requirement understanding, IC selection, package and pin extraction, schematic graph construction, rule checking, simulation support, layout suggestion, and production-file preparation. Agents are useful here because each step has different evidence, failure modes, and verification criteria.

**Design-to-manufacturing loop.** A PCB assistant is only useful if its outputs survive real engineering checks. The workflow therefore emphasizes structured artifacts, EDA importability, ERC/DRC-style validation, prototype feedback, and manufacturing constraints instead of free-form diagram descriptions.

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-iclagent-pipeline.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 5  Agentic workflows decompose footprint labeling into detection, classification, parameter planning, reasoning, and description generation.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-iclagent-workflow.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 6  LMM agents can mirror expert PCB-engineering steps while preserving intermediate evidence for inspection.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-iclagent-package-types.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 7  Robust PCB intelligence must handle diverse IC package types and dense, visually small geometric details.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-omnisch-annotation.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 8  Automated schematic annotation turns source-code-derived circuit diagrams into symbol, pin, graph, and schematic objects.
</div>

## Research Foundation

The publications below contribute core capabilities to this larger direction. They establish datasets and reasoning tasks for IC footprint geometry, multi-agent footprint labeling, and PCB schematic graph understanding. Together, these results form a research base for moving from visual circuit understanding toward practical PCB design automation.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-omnisch-tasks.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 9  Schematic understanding requires object detection, topology reasoning, graph construction, QA, and automated annotation.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-circuit-intelligence-omnisch-benchmark.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 10  Schematic-level benchmarks organize pins, symbols, netlist graphs, source code, and metadata into structured multimodal objects.
</div>

## Why It Matters

The long-term opportunity is not just faster annotation or better diagram QA. It is a new interface for hardware design: a system where engineers can state intent, inspect model evidence, revise constraints, and receive machine-checkable circuit assets that remain compatible with existing EDA and manufacturing pipelines.

This can lower the barrier to PCB design for small teams, reduce avoidable footprint and connectivity errors, shorten design-to-prototype cycles, and build reusable design knowledge for intelligent EDA and electronics manufacturing.

***

## Publications

<div hidden>
{% cite wang-icml26 %}
{% cite wang-eccv26 %}
{% cite lu-eccv26 %}
</div>
