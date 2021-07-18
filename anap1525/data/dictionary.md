---
layout: page
title: Data Dictionary
---

## Purpose
Adds details that are not typically included in DFDs, ERDs, or other documentation. There are many types of data dictionaries available and they focus on different jobs.

## Terms
* **Data Attribute**: is the smallest piece of data that has meaning to the end-users and the business.
* **Data Structures**: are specific arrangements of data attributes that define the organization of a single instance data needed for a task such as a screen, report or data flow.

## 3 Basic Types
* **Sequence** – a group of data attributes that occur one after another in order.
* **Selection** – one or more attributes chosen from a set of attributes.
* **Repetition** – a group of one or more attributes that may have multiple instances within a larger data structure.

## Data Structure Symbols
* `=`: means “consists of” or “is composed of”
* `+`: means “and” and designates a sequence
* `[...]`: means only one of the attributes listed within the brackets may be present, and designates selection
* `{...}`: means the attributes within the braces may occur many times for one instance of the main data structure and designates repetition
* `(...)`: means that the attribute(s) within the parentheses are optional and may not always be present

## Sequence Data Structure

**Document Example** | **Data Structure**
---------------------|-------------------
put picture here | **Wage And Tax Statement** = Taxpayer Identification Number + Taxpayer Name + Taxpayer Address + Wages, Tips And Compensation + Federal Tax Withheld + ...


### [ANAP1525 Home](../)