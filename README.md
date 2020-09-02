#  
```zsh
# libera porta 8000
sudo ufw allow 8000

sudo iptables -A FORWARD -p tcp --dport 8000 -j ACCEPT
```


## Criando minha api em Rust
```zsh
mkdir rust-api
cd rust-api
asdf local rust 1.46.0
cargo new rust-api --bin

rustup default nightly
rustup update && cargo update

# start postgresql and seed the database
psql -f init.sql
cargo install diesel_cli --no-default-features --features "postgres"
diesel migration run

cargo run
```

## Compilando rust
```zsh
cd rust-api
cargo build --release && cd target/release/
```


## Principais frameworks usadas
```zsh
# Rocket — web framework for writing fast web applications 
(https://rocket.rs/)

# Serde — framework for serializing and deserializing Rust data structures
(https://serde.rs/)

# Diesel — safe, extensible ORM and query builder
(http://diesel.rs/)
```