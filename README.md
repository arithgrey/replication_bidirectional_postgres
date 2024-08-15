# replication_bidirectional_postgres

# cloudsql.enable_pglogical = on
# max_wal_senders = 10
# max_worker_processes = 15
# max_wal_size = 128
# wal_sender_timeout = 60000
# wal_receiver_timeout = 60000
# hot_standby_feedback = on
# cloudsql.logical_decoding = on
# max_logical_replication_workers = 4
# track_commit_timestamp=on
# pglogical.conflict_resolution = last_update_wins
# max_replication_slots = 10
# pglogical.use_spi = off
# tcp_keepalives_idle = 120
# autovacuum = on
# max_connections = 100

# psql -U postgres -c "CREATE ROLE replicator WITH REPLICATION LOGIN PASSWORD 'replica_password';"
# psql -U postgres
# psql -U postgres -d mydb

# INSERT INTO users (username, email) VALUES ('alice', 'alice@example.com');
# INSERT INTO users (username, email) VALUES ('bob', 'bob@example.com');
# INSERT INTO users (username, email) VALUES ('carol', 'carol@example.com');
# select * from users;
# docker exec -it postgres-primary psql -U postgres -d mydb -c "INSERT INTO users (username, email) VALUES ('testuser', 'testuser@example.com');"
# docker exec -it postgres-secondary psql -U postgres -d mydb -c "SELECT * FROM users;"
# docker exec -it postgres-secondary psql -U postgres -c "CREATE DATABASE mydb;"
