# pgsql-rpm: build rpm for PostgreSQL Extensions

--------

## What's inside?

PostgreSQL Extensions that **NOT** included in the official PGDG repo.

22 Extensions build with `c/c++`:

| Extension Name                                                     |             | SPEC                                                   | Comment            |
|--------------------------------------------------------------------|-------------|--------------------------------------------------------|--------------------|
| [scws](https://github.com/hightman/scws)                           | v1.2.3      | [scws.spec](SPECS/scws.spec)                           | Deps of zhparser   |
| [libduckdb](https://github.com/duckdb/duckdb)                      | v1.0.0      | [libduckdb.spec](SPECS/libduckdb.spec)                 | Deps of duckdb_fdw |
| [duckdb_fdw](https://github.com/alitrack/duckdb_fdw)               | v1.0.0      | [pg_graphql.spec](SPECS/duckdb_fdw.spec)               |                    |
| [zhparser](https://github.com/amutu/zhparser)                      | v2.2        | [zhparser.spec](SPECS/zhparser.spec)                   |                    |
| [pg_roaringbitmap](https://github.com/ChenHuajun/pg_roaringbitmap) | v0.5.4      | [pg_roaringbitmap.spec](SPECS/pg_roaringbitmap.spec)   |                    |
| [pgjwt](https://github.com/michelp/pgjwt)                          | v0.2.0      | [pgjwt.spec](SPECS/pgjwt.spec)                         |                    |
| [vault](https://github.com/supabase/vault)                         | v0.2.9      | [vault.spec](SPECS/vault.spec)                         |                    |
| [hydra](https://github.com/hydradatabase/)                         | v1.1.2      | [hydra.spec](SPECS/hydra.spec)                         |                    |
| [age](https://github.com/apache/age)                               | v1.5.0      | [age.spec](SPECS/age.spec)                             | 1.4 with PG15      |
| [plv8](https://github.com/plv8/plv8)                               | v3.2.2      | [plv8.spec](SPECS/plv8)                                |                    |
| [pg_tde](https://github.com/Percona-Lab/pg_tde/tree/1.0.0-beta)    | v1.0.0-beta | [pg_tde.spec](SPECS/pg_tde)                            |                    |
| [md5hash](https://github.com/tvondra/md5hash)                      | v1.0.1      | [md5hash.spec](SPECS/md5hash)                          |                    |
| [hunspell](https://github.com/postgrespro/hunspell_dicts)          | v1.0        | [hunspell.spec](SPECS/hunspell.spec)                   |                    |                 
| [pg_sqlog](https://github.com/kouber/pg_sqlog)                     | v1.6        | [pg_sqlog.spec](SPECS/pg_sqlog.spec)                   |                    |      
| [pg_proctab](https://gitlab.com/pg_proctab/pg_proctab)             | v0.0.10     | [pg_proctab.spec](SPECS/pg_proctab.spec)               |                    |              
| [pg_hashids](https://github.com/iCyberon/pg_hashids)               | v1.3        | [pg_hashids.spec](SPECS/pg_hashids.spec)               |                    |            
| [postgres_shacrypt](https://github.com/dverite/postgres-shacrypt)  | v1.1        | [postgres_shacrypt.spec](SPECS/postgres_shacrypt.spec) |                    |                         
| [permuteseq](https://github.com/dverite/permuteseq)                | v1.2.2      | [permuteseq.spec](SPECS/permuteseq.spec)               |                    |
| [supautils](https://github.com/supabase/supautils)                 | v2.2.1      | [supautils.spec](SPECS/supautils.spec)                 |                    |
| [pg_similarity](https://github.com/eulerto/pg_similarity)          | v1.0        | [pg_similarity.spec](SPECS/pg_similarity.spec)         |                    |
| [imgsmlr](https://github.com/postgrespro/imgsmlr)                  | v1.0        | [imgsmlr.spec](SPECS/imgsmlr.spec)                     |                    |
| [pg_filedump](https://github.com/df7cb/pg_filedump)                | v17.0       |                                                        |

16 Extension build with `rust` & `pgrx`:

| Vendor        | Name                                                                       | Version | PGRX                                                                                            | License                                                                     | PG Ver         | Deps                 |
|---------------|----------------------------------------------------------------------------|---------|-------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------|----------------|----------------------|
| PostgresML    | [pgml](https://github.com/postgresml/postgresml)                           | v2.9.2  | [v0.11.3](https://github.com/postgresml/postgresml/blob/master/pgml-extension/Cargo.lock#L1785) | [MIT](https://github.com/postgresml/postgresml/blob/master/MIT-LICENSE.txt) | 16,15,14       |                      |
| ParadeDB      | [pg_search](https://github.com/paradedb/paradedb/tree/dev/pg_search)       | v0.8.6  | [v0.11.3](https://github.com/paradedb/paradedb/blob/dev/pg_search/Cargo.toml#L36)               | [AGPLv3](https://github.com/paradedb/paradedb/blob/dev/LICENSE)             | 16,15,14,13,12 |                      |
| ParadeDB      | [pg_lakehouse](https://github.com/paradedb/paradedb/tree/dev/pg_lakehouse) | v0.8.6  | [v0.11.3](https://github.com/paradedb/paradedb/blob/dev/pg_lakehouse/Cargo.toml#L26)            | [AGPLv3](https://github.com/paradedb/paradedb/blob/dev/LICENSE)             | 16,15          |                      |
| Supabase      | [pg_graphql](https://github.com/supabase/pg_graphql)                       | v1.5.7  | [v0.11.3](https://github.com/supabase/pg_graphql/blob/master/Cargo.toml#L17)                    | [Apache-2.0](https://github.com/supabase/pg_graphql/blob/master/LICENSE)    | 16,15          |                      |
| Supabase      | [pg_jsonschema](https://github.com/supabase/pg_jsonschema)                 | v0.3.1  | [v0.11.3](https://github.com/supabase/pg_jsonschema/blob/master/Cargo.toml#L19)                 | [Apache-2.0](https://github.com/supabase/pg_jsonschema/blob/master/LICENSE) | 16,15,14,13,12 |                      |
| Supabase      | [wrappers](https://github.com/supabase/wrappers)                           | v0.4.1  | [v0.11.3](https://github.com/supabase/wrappers/blob/main/Cargo.lock#L4254)                      | [Apache-2.0](https://github.com/supabase/wrappers/blob/main/LICENSE)        | 16,15,14       |                      |
| Tembo         | [pgmq](https://github.com/tembo-io/pgmq)                                   | v1.2.1  | v0.11.3                                                                                         | [PostgreSQL](https://github.com/tembo-io/pgmq)                              | 16,15,14,13,12 |                      |
| Tembo         | [pg_tier](https://github.com/tembo-io/pg_tier)                             | v0.0.4  | v0.11.3                                                                                         | [Apache-2.0](https://github.com/tembo-io/pg_tier/blob/main/LICENSE)         | 16             | pgmq, parquet_s3_fdw |
| Tembo         | [pg_vectorize](https://github.com/tembo-io/pg_vectorize)                   | v0.17.0 | v0.11.3                                                                                         | [PostgreSQL](https://github.com/tembo-io/pg_vectorize/blob/main/LICENSE)    | 16,15,14       | pgmq, pg_cron        |
| Tembo         | [pg_later](https://github.com/tembo-io/pg_later)                           | v0.1.1  | v0.11.3                                                                                         | [PostgreSQL](https://github.com/tembo-io/pg_later/blob/main/LICENSE)        | 16,15,14,13    | pgmq                 |
| VADOSWARE     | [pg_idkit](https://github.com/VADOSWARE/pg_idkit)                          | v0.2.3  | v0.11.3                                                                                         | [Apache-2.0](https://github.com/VADOSWARE/pg_idkit/blob/main/LICENSE)       | 16,15,14,13,12 |                      |
| pgsmcrypto    | [pgsmcrypto](https://github.com/zhuobie/pgsmcrypto)                        | v0.1.0  | v0.11.3                                                                                         | [MIT](https://github.com/zhuobie/pgsmcrypto/blob/main/LICENSE)              | 16,15,14,13,12 |                      |
| kelvich       | [pg_tiktoken](https://github.com/kelvich/pg_tiktoken)                      | v0.0.1  | [v0.10.2](https://github.com/kelvich/pg_tiktoken/blob/main/Cargo.toml)                          | [Apache-2.0](https://github.com/kelvich/pg_tiktoken/blob/main/LICENSE)      | 16,15,14,13,12 |                      |
| rustprooflabs | [pgdd](https://github.com/rustprooflabs/pgdd)                              | v0.5.2  | [v0.10.2](https://github.com/rustprooflabs/pgdd/blob/main/Cargo.toml#L25)                       | [MIT](https://github.com/zhuobie/pgsmcrypto/blob/main/LICENSE)              | 16,15,14,13,12 |                      |
| timescale     | [vectorscale](https://github.com/timescale/pgvectorscale)                  | v0.2.0  | [v0.11.4](https://github.com/timescale/pgvectorscale/blob/main/pgvectorscale/Cargo.toml#L17)    | [PostgreSQL](https://github.com/timescale/pgvectorscale/blob/main/LICENSE)  | 16,15,14,13,12 |                      |
| kaspermarstal | [plprql](https://github.com/kaspermarstal/plprql)                          | v0.1.0  | [v0.11.4](https://github.com/kaspermarstal/plprql/blob/main/Cargo.toml#L21)                     | [Apache-2.0](https://github.com/kaspermarstal/plprql/blob/main/LICENSE)     | 16,15,14,13,12 |                      |


9 Extensions that is obsolete due to included in PGDG or no longer maintained:

| Extension Name                                                       | SPEC   | Comment                     |
|----------------------------------------------------------------------|--------|-----------------------------|
| [pg_analytics](https://github.com/paradedb/pg_analytics)             | v0.6.1 | No longer maintained        |
| [pg_sparse](https://github.com/paradedb/paradedb/tree/dev/pg_sparse) | v0.6.1 | No longer maintained        |
| [pg_net](https://github.com/supabase/pg_net)                         | v0.9.2 | PGDG included, N/A in el7   |
| [pg_tle](https://github.com/aws/pg_tle)                              | v1.3.4 | PGDG included, for el7 only |
| [pg_bigm](https://github.com/pgbigm/pg_bigm)                         | v1.2   | PGDG included, for el7 only |
| [pgsql-http](https://github.com/pramsey/pgsql-http)                  | v1.6.0 | PGDG included, for el7 only |
| [pgsql-gzip](https://github.com/pramsey/pgsql-gzip)                  | v1.0.0 | PGDG included, for el7 only |
| [pg_dirtyread](https://github.com/df7cb/pg_dirtyread)                | v2.7   | PGDG included, for el7 only |
| [pointcloud](https://github.com/pgpointcloud/pointcloud)             | v1.2.5 | PGDG included, for el7 only |



----------

## Environment

```bash
# launch pigsty 3-node el build env
cd ~/pigsty; make clean; make rpm
./node.yml -i files/pigsty/rpmbuild.yml -t node_repo,node_pkg

# create rpmbuild fhs
rpmdev-setuptree

# install ad hoc packages 
sudo yum groupinstall --nobest -y 'Development Tools';    # el8 only logic
sudo cpanm FindBin; perl -MFindBin -e 1                   # el9 only logic 

# push source to el building VM
make ps      # make push-ss (specs & sources)
```

EL Building Recipe:

```bash
make 
```


--------

## License

Maintainer: Ruohang Feng / [@Vonng](https://vonng.com/en/) ([rh@vonng.com](mailto:rh@vonng.com))

License: [Apache 2.0](LICENSE)
