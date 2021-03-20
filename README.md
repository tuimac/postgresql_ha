# postgresql_ha
PoC for PostgreSQL High Availability on Docker environment.

- Frontend: easy console to throw API to backend(non framework)
- Backend: spring boot
- Database: PostgreSQL with container placed on multi host. Test for switch sync to async replication.

## First Step
Make sure that creating two postgresql container on single host. Use different port and switched by NLB.

## Second Step
Multi host test.
