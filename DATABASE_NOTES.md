# Database implementation notes

## Confirmed in the supplied SQL
- 12 `CREATE TABLE` definitions: SCHEDULE, MAINTENANCELOG, PAYMENT, INVOICE, SHIPMENT, VEHICLE, WAREHOUSE, CLIENT, SUPPLIER, CARGOTYPE, STAFFROLE and TRANSPORTMODE.
- Primary keys, unique constraints and validation constraints.
- Foreign-key relationships across the logistics entities.
- `TRG_SHIPMENT_BI`, a `BEFORE INSERT` row trigger.

## Dependencies and limitations
1. `SEQ_SHIPMENT` is referenced by `TRG_SHIPMENT_BI` but was absent from the original file. The portfolio setup script defines it.
2. `FK_WAREHOUSE_MANAGER` references `STAFF(STAFFID)`, but no STAFF table definition was supplied. The portfolio setup script omits only this foreign-key statement; it does not invent the missing table.
3. The original file adds some foreign keys before all referenced tables have been created. The portfolio setup script orders table creation first and foreign keys afterwards.
4. No INSERT statements or sample dataset were present in the supplied SQL file.
5. Stored procedures, views, indexes, partitions and clustering are not included in this SQL file. If these were completed in separate coursework files, add them separately and document them accurately.
