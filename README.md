# pg_dump-and-pg_restore-docker
Get pg_dump from a Docker Container and pg_restore into another in few steps.

## GENERATING
1. `⁠docker exec -t your_db_container pg_dump -U your_username -F c -d your_database -f /tmp/your_database.dump`
2.⁠ `⁠docker cp your_db_container:/tmp/your_database.dump ~/your_database.dump`

Tip: To verify dump use `pg_restore -l your_database.dump`

## RESTORING
1. `⁠docker cp ./your_database.dump <container_db_name>:/your_database.dump`
2.⁠ `⁠docker exec -t <container_db_name> pg_restore -U <db_user> -d <db_name> --disable-triggers your_database.dump`


## EXCEPTIONS
1. To include all the data after the data dump restore, remove --data-only in the below code
 `⁠docker exec -t <container_db_name> pg_restore -U <db_user> -d <db_name> --disable-triggers  your_database.dump`


Credits
### Emmanuel Owusu (coding-rev)
- Software/Backend/Full-stack Engineer

### Bernard Owusu-Appiah (bernard-oa)
- Snr Software Engineer


Working | Django | Python | Codingrev | Software Engineer
