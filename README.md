# PCB Printer
# PCB Printer — CAD Design

## Overview

This repository contains the **CAD models and mechanical design files** developed for a prototype **additive PCB printer**.

The project explores the use of **Direct Ink Writing (DIW)** to fabricate conductive traces by depositing conductive ink directly onto a substrate, as an alternative to conventional subtractive PCB fabrication.

The printer was designed around a **syringe-based piston extrusion system** and a **belt-driven X-Y motion system**, with the printhead positioning and ink deposition controlled through a GRBL-based CNC system.

---

## Project Objectives

The main objective was to develop a low-cost prototype PCB printer capable of depositing conductive ink along programmed toolpaths.

The mechanical system was designed to:

- Precisely position the extrusion head in the X-Y plane
- Control conductive ink deposition using a syringe and plunger mechanism
- Provide a modular mechanical structure for prototyping and further development
- Support future integration of curing and PCB-printing processes
- Enable rapid prototyping of custom PCB geometries

---

## System Architecture

The printer consists primarily of the following subsystems:

### 1. X-Y Linear Motion System

A **belt-driven Cartesian motion system** was selected for positioning the printhead.

The system consists of:

- Stepper motors
- Timing belts
- Pulleys
- Linear rails/rods
- Structural components

The belt drive converts the rotational motion of the stepper motors into translational motion of the printhead.

A belt-driven system was selected as a practical balance between:

- Speed
- Accuracy
- Cost
- Ease of fabrication
- Ease of implementation

---

### 2. Syringe-Based Extrusion System

The extrusion system uses a **mechanically driven syringe and plunger** to deposit conductive ink.

A stepper motor drives the plunger, allowing the amount of material being deposited to be controlled through the displacement of the syringe plunger.

The piston-based approach was selected because it provides:

- Controlled extrusion volume
- Repeatable material deposition
- Compatibility with conductive inks
- Direct control over extrusion rate

The extrusion mechanism was designed with high-viscosity conductive inks in mind.

---

### 3. Z-Axis / Extrusion Control

The Z-axis is used to drive the syringe plunger rather than simply positioning the printhead.

The extrusion motion is coordinated with the X-Y movement so that the amount of ink deposited remains consistent as the printhead moves along the PCB toolpath.

The control system therefore treats the Z-axis as an **extrusion axis**.

---

## CAD Design

The CAD files in this repository represent the mechanical components and assemblies developed during the design phase of the PCB printer.

The design includes components associated with:

- Printer frame
- X-Y motion system
- Belt and pulley arrangement
- Linear guides
- Stepper motor mounting
- Syringe extrusion mechanism
- Printhead assembly
- Mechanical supports and brackets
- Overall printer assembly

The CAD models were developed as part of the transition from the initial concept to the final prototype.

---

## Manufacturing Approach

The printer uses an **additive PCB fabrication** approach.

Instead of removing unwanted copper through chemical etching, conductive ink is deposited directly onto the substrate.

### Printing Process

```text
PCB Design
     ↓
Gerber File (.GTL)
     ↓
Toolpath Generation
     ↓
G-Code
     ↓
GRBL Controller
     ↓
X-Y Motion + Syringe Extrusion
     ↓
Conductive Trace Deposition
     ↓
Curing
