# RailUK Logistics Database Management System

## Project overview
A relational database developed for a logistics-company case study as part of the Database Systems Development module at Birmingham City University. The schema models customers, suppliers, shipments, vehicles, warehouses, transport modes, cargo types, schedules, maintenance, invoices, payments and staff roles.

## Technologies
- Oracle SQL
- PL/SQL
- Oracle APEX (development environment)

## What the submitted SQL demonstrates
- 12 table definitions for core logistics entities.
- Primary keys, foreign keys, unique constraints and CHECK constraints.
- Relationships between shipments, clients, vehicles, warehouses, schedules, invoices and payments.
- A `BEFORE INSERT` shipment trigger for ID assignment, weight validation and default values.
- A shipment sequence reference (`SEQ_SHIPMENT`).

## Repository contents
- `original_submission.sql` — original SQL submission, preserved without edits.
- `railuk_logistics_setup.sql` — reorganised deployment version based on the original, with table creation before foreign-key creation and a sequence added for the trigger dependency.
- `DATABASE_NOTES.md` — implementation notes and known dependencies.

## Setup notes and known dependencies
The original trigger references `SEQ_SHIPMENT`, but the supplied original SQL file did not define that sequence. The reorganised setup script adds `SEQ_SHIPMENT` before creating the trigger.

The original `WAREHOUSE` table contains `MANAGERSTAFFID`, and its foreign-key constraint references `STAFF(STAFFID)`. A `STAFF` table definition was not present in the supplied SQL file. To avoid inventing coursework schema, the reorganised setup script leaves this one foreign-key constraint out. If the original STAFF table is recovered, add the relationship after creating that table.

The supplied SQL is a schema-focused script. It does not include sample-data inserts, the ERD image, or the separate query/procedure scripts, so these are not represented as included deliverables here.

## How to use
Run `railuk_logistics_setup.sql` in an Oracle SQL environment (such as Oracle APEX SQL Workshop or SQL Developer) using a clean schema. Review the setup notes first. The script is a reorganised portfolio copy; `original_submission.sql` is retained for comparison.

## Academic project
This repository presents university coursework for portfolio and learning purposes. It is not represented as a production-ready logistics platform.
