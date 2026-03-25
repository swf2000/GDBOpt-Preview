Overall, we select 42 query optimization issues for Neo4j, 11 query optimizatio issues for Memgraph, 29 query optimizatio issues for Redisgraph, and 20 query optimizatio issues for kuzu. The following table contains the links for these issues, and our empirical study results concerning their root causes, manfiestations, and fix strategies. 

- examples: stores all program synthesis problems
  - `brahma.rs`: stores the data set composed of tf-coder data set and stackoverflow original problems
  - `myexample.rs`: stores own data set
  - You can add other data sets in this directory
- result: Stores the running results, divided into 5 minutes, 10 minutes, and 15 minutes
  - The datasets are divided into 3 parts. Stackoverflow original problems output files' names start with `new_stackoverflow`, tf-coder data set output files' names starts with `test`, `duplicate`, `simple`, `google`, `stackoverflow` or `autopandas`, own data set output files' names starts with `prog`
- src: the core part of program synthesis
  - BayesNetwork: the storage location of the Bayesian network
    - data: the data for building the Bayesian network
    - `bayes_main.py`: code for building the Bayesian network, for details, refer to `Readme.md`
  - createBayesNetwork: The process of building a Bayesian network, for details, refer to `readme.md`
  - `operator.rs`: records all the contents that appear in the project, that is, variable definitions, free variables (large constants) and components
  - `builder.rs`: uses the contents defined in `operator.rs` in examples
  - `component.rs`: Encode the components defined in `operator.rs`
  - `fake_logging.rs`: File used for simulation output, no need to process
  - `lib.rs`: The code for program synthesis, filtering algorithms and filtering conditions, and components used during synthesis are all in this directory
- `Cargo.toml`: Rust package configuration file, which can be set if third-party libraries need to be installed or adjusted
- `rustfmt.toml`: Format rust code


| ID  | GDBMS  | Issue|
|------|------|------|
| 1 |Neo4j|[Neo4j-4315](https://github.com/neo4j/neo4j/issues/4315) |
| 2 |Neo4j|[Neo4j-5921](https://github.com/neo4j/neo4j/issues/5921) |
| 3 |Neo4j|[Neo4j-5986](https://github.com/neo4j/neo4j/issues/5986) |
| 4 |Neo4j|[Neo4j-6615](https://github.com/neo4j/neo4j/issues/6615) |
| 5 |Neo4j|[Neo4j-6947](https://github.com/neo4j/neo4j/issues/6947) |
| 6 |Neo4j|[Neo4j-6956](https://github.com/neo4j/neo4j/issues/6956) |
| 7 |Neo4j|[Neo4j-7415](https://github.com/neo4j/neo4j/issues/7415) |
| 8 |Neo4j|[Neo4j-9055](https://github.com/neo4j/neo4j/issues/9055) |
| 9 |Neo4j|[Neo4j-9435](https://github.com/neo4j/neo4j/issues/9435) |
| 10 |Neo4j|[Neo4j-10100](https://github.com/neo4j/neo4j/issues/10100) |
| 11 |Neo4j|[Neo4j-10831](https://github.com/neo4j/neo4j/issues/10831) |
| 12 |Neo4j|[Neo4j-11463](https://github.com/neo4j/neo4j/issues/11463) |
| 13 |Neo4j|[Neo4j-11677](https://github.com/neo4j/neo4j/issues/11677) |
| 14 |Neo4j|[Neo4j-11944](https://github.com/neo4j/neo4j/issues/11944) |
| 15 |Neo4j|[Neo4j-12195](https://github.com/neo4j/neo4j/issues/12195) |
| 16 |Neo4j|[Neo4j-12225](https://github.com/neo4j/neo4j/issues/12225) |
| 17 |Neo4j|[Neo4j-12232](https://github.com/neo4j/neo4j/issues/12232) |
| 18 |Neo4j|[Neo4j-12247](https://github.com/neo4j/neo4j/issues/12247) |
| 19 |Neo4j|[Neo4j-12329](https://github.com/neo4j/neo4j/issues/12329) |
| 20 |Neo4j|[Neo4j-12484](https://github.com/neo4j/neo4j/issues/12484) |
| 21 |Neo4j|[Neo4j-12583](https://github.com/neo4j/neo4j/issues/12583) |
| 22 |Neo4j|[Neo4j-12618](https://github.com/neo4j/neo4j/issues/12618) |
| 23 |Neo4j|[Neo4j-12759](https://github.com/neo4j/neo4j/issues/12759) |
| 24 |Neo4j|[Neo4j-12760](https://github.com/neo4j/neo4j/issues/12760) |
| 25 |Neo4j|[Neo4j-12876](https://github.com/neo4j/neo4j/issues/12876) |
| 26 |Neo4j|[Neo4j-12926](https://github.com/neo4j/neo4j/issues/12926) |
| 27 |Neo4j|[Neo4j-12973](https://github.com/neo4j/neo4j/issues/12973) |
| 28 |Neo4j|[Neo4j-12982](https://github.com/neo4j/neo4j/issues/12982) |
| 29 |Neo4j|[Neo4j-13034](https://github.com/neo4j/neo4j/issues/13034) |
| 30 |Neo4j|[Neo4j-13036](https://github.com/neo4j/neo4j/issues/13036) |
| 31 |Neo4j|[Neo4j-13147](https://github.com/neo4j/neo4j/issues/13147) |
| 32 |Neo4j|[Neo4j-13166](https://github.com/neo4j/neo4j/issues/13166) |
| 33 |Neo4j|[Neo4j-13169](https://github.com/neo4j/neo4j/issues/13169) |
| 34 |Neo4j|[Neo4j-13189](https://github.com/neo4j/neo4j/issues/13189) |
| 35 |Neo4j|[Neo4j-13210](https://github.com/neo4j/neo4j/issues/13210) |
| 36 |Neo4j|[Neo4j-13245](https://github.com/neo4j/neo4j/issues/13245) |
| 37 |Neo4j|[Neo4j-13246](https://github.com/neo4j/neo4j/issues/13246) |
| 38 |Neo4j|[Neo4j-13354](https://github.com/neo4j/neo4j/issues/13354) |
| 39 |Neo4j|[Neo4j-13382](https://github.com/neo4j/neo4j/issues/13382) |
| 40 |Neo4j|[Neo4j-13427](https://github.com/neo4j/neo4j/issues/13427) |
| 41 |Neo4j|[Neo4j-13486](https://github.com/neo4j/neo4j/issues/13486) |
| 42 |Neo4j|[Neo4j-13552](https://github.com/neo4j/neo4j/issues/13552) |
|------|------|------|
| 43 |Memgraph|[Memgraph-1293](https://github.com/memgraph/memgraph/issues/1293) |
| 44 |Memgraph|[Memgraph-1295](https://github.com/memgraph/memgraph/issues/1295) |
| 45 |Memgraph|[Memgraph-1416](https://github.com/memgraph/memgraph/issues/1416) |
| 46 |Memgraph|[Memgraph-1486](https://github.com/memgraph/memgraph/issues/1486) |
| 47 |Memgraph|[Memgraph-1592](https://github.com/memgraph/memgraph/issues/1592) |
| 48 |Memgraph|[Memgraph-1611](https://github.com/memgraph/memgraph/issues/1611) |
| 49 |Memgraph|[Memgraph-1648](https://github.com/memgraph/memgraph/issues/1648) |
| 50 |Memgraph|[Memgraph-1958](https://github.com/memgraph/memgraph/issues/1958) |
| 51 |Memgraph|[Memgraph-2116](https://github.com/memgraph/memgraph/issues/2116) |
| 52 |Memgraph|[Memgraph-2456](https://github.com/memgraph/memgraph/issues/2456) |
| 53 |Memgraph|[Memgraph-2491](https://github.com/memgraph/memgraph/issues/2491) |
|------|------|------|
| 54 |Redisgraph|[Redisgraph-135](https://github.com/RedisGraph/RedisGraph/issues/135) |
| 55 |Redisgraph|[Redisgraph-192](https://github.com/RedisGraph/RedisGraph/issues/192) |
| 56 |Redisgraph|[Redisgraph-249](https://github.com/RedisGraph/RedisGraph/issues/249) |
| 57 |Redisgraph|[Redisgraph-456](https://github.com/RedisGraph/RedisGraph/issues/456) |
| 58 |Redisgraph|[Redisgraph-471](https://github.com/RedisGraph/RedisGraph/issues/471) |
| 59 |Redisgraph|[Redisgraph-512](https://github.com/RedisGraph/RedisGraph/issues/512) |
| 60 |Redisgraph|[Redisgraph-634](https://github.com/RedisGraph/RedisGraph/issues/634) |
| 61 |Redisgraph|[Redisgraph-772](https://github.com/RedisGraph/RedisGraph/issues/772) |
| 62 |Redisgraph|[Redisgraph-792](https://github.com/RedisGraph/RedisGraph/issues/792) |
| 63 |Redisgraph|[Redisgraph-818](https://github.com/RedisGraph/RedisGraph/issues/818) |
| 64 |Redisgraph|[Redisgraph-858](https://github.com/RedisGraph/RedisGraph/issues/858) |
| 65 |Redisgraph|[Redisgraph-869](https://github.com/RedisGraph/RedisGraph/issues/869) |
| 66 |Redisgraph|[Redisgraph-1036](https://github.com/RedisGraph/RedisGraph/issues/1036) |
| 67 |Redisgraph|[Redisgraph-1068](https://github.com/RedisGraph/RedisGraph/issues/1068) |
| 68 |Redisgraph|[Redisgraph-1096](https://github.com/RedisGraph/RedisGraph/issues/1096) |
| 69 |Redisgraph|[Redisgraph-1270](https://github.com/RedisGraph/RedisGraph/issues/1270) |
| 70 |Redisgraph|[Redisgraph-1305](https://github.com/RedisGraph/RedisGraph/issues/1305) |
| 71 |Redisgraph|[Redisgraph-1309](https://github.com/RedisGraph/RedisGraph/issues/1309) |
| 72 |Redisgraph|[Redisgraph-1313](https://github.com/RedisGraph/RedisGraph/issues/1313) |
| 73 |Redisgraph|[Redisgraph-1346](https://github.com/RedisGraph/RedisGraph/issues/1346) |
| 74 |Redisgraph|[Redisgraph-1394](https://github.com/RedisGraph/RedisGraph/issues/1394) |
| 75 |Redisgraph|[Redisgraph-1455](https://github.com/RedisGraph/RedisGraph/issues/1455) |
| 76 |Redisgraph|[Redisgraph-1491](https://github.com/RedisGraph/RedisGraph/issues/1491) |
| 77 |Redisgraph|[Redisgraph-1493](https://github.com/RedisGraph/RedisGraph/issues/1493) |
| 78 |Redisgraph|[Redisgraph-1688](https://github.com/RedisGraph/RedisGraph/issues/1688) |
| 79 |Redisgraph|[Redisgraph-2206](https://github.com/RedisGraph/RedisGraph/issues/2206) |
| 80 |Redisgraph|[Redisgraph-2424](https://github.com/RedisGraph/RedisGraph/issues/2424) |
| 81 |Redisgraph|[Redisgraph-2631](https://github.com/RedisGraph/RedisGraph/issues/2631) |
| 82 |Redisgraph|[Redisgraph-2836](https://github.com/RedisGraph/RedisGraph/issues/2836) |
|------|------|------|
| 83 |Kuzu|[Kuzu-103](https://github.com/kuzudb/kuzu/issues/103) |
| 84 |Kuzu|[Kuzu-112](https://github.com/kuzudb/kuzu/issues/112) |
| 85 |Kuzu|[Kuzu-127](https://github.com/kuzudb/kuzu/issues/127) |
| 86 |Kuzu|[Kuzu-248](https://github.com/kuzudb/kuzu/issues/248) |
| 87 |Kuzu|[Kuzu-259](https://github.com/kuzudb/kuzu/issues/259) |
| 88 |Kuzu|[Kuzu-302](https://github.com/kuzudb/kuzu/issues/302) |
| 89 |Kuzu|[Kuzu-305](https://github.com/kuzudb/kuzu/issues/305) |
| 90 |Kuzu|[Kuzu-327](https://github.com/kuzudb/kuzu/issues/327) |
| 91 |Kuzu|[Kuzu-419](https://github.com/kuzudb/kuzu/issues/419) |
| 92 |Kuzu|[Kuzu-584](https://github.com/kuzudb/kuzu/issues/584) |
| 93 |Kuzu|[Kuzu-606](https://github.com/kuzudb/kuzu/issues/606) |
| 94 |Kuzu|[Kuzu-823](https://github.com/kuzudb/kuzu/issues/823) |
| 95 |Kuzu|[Kuzu-2202](https://github.com/kuzudb/kuzu/issues/2202) |
| 96 |Kuzu|[Kuzu-2360](https://github.com/kuzudb/kuzu/issues/2360) |
| 97 |Kuzu|[Kuzu-2648](https://github.com/kuzudb/kuzu/issues/2648) |
| 98 |Kuzu|[Kuzu-3606](https://github.com/kuzudb/kuzu/issues/3606) |
| 99 |Kuzu|[Kuzu-4281](https://github.com/kuzudb/kuzu/issues/4281) |
| 100 |Kuzu|[Kuzu-4967](https://github.com/kuzudb/kuzu/issues/4967) |
| 101 |Kuzu|[Kuzu-5040](https://github.com/kuzudb/kuzu/issues/5040) |
| 102 |Kuzu|[Kuzu-5177](https://github.com/kuzudb/kuzu/issues/5177) |
