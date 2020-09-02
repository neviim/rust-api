# Uma API basica em Rust 
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

[Rocket](https://rocket.rs/) — web framework for writing fast web applications 
[Diesel](http://diesel.rs/) — safe, extensible ORM and query builder 
[Serde](https://serde.rs/)  — framework for serializing and deserializing Rust data structures 
