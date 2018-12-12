# Instalation
## Instalation of Elixir and Phoenix
***
__Ignore this block if you already installed Elixir 1.7+ and Phoenix 1.4__
***

At first you should install Elixir. Go to [Installation guide](https://elixir-lang.org/install.html) and choose your operating system' variant.

After that, according to [Phoenix installation guides](https://hexdocs.pm/phoenix/installation.html), you shoul do:
```bash
mix local.hex
```
to install latest version of Hex package manager, and
```bash
mix archive.install hex phx_new 1.4.0
```
to install Phoenix 1.4.

## Creating a project

Go to you `projects` folder (there you going to develop), and run
```bash
mix phx.new project_name
```
But I personnally recommend to use `--umbrella` flag to create application divided into `/apps` folder. It will be easily to develop and maintain. Important! In `umbrella` mode `mix phx.routes` need to specify `ProjectName.Router` to watch them.

After that you can do `Y` if you want to install all dependencies, or do it later by:
```bash
cd project_name/
mix deps.get
```

## Congiguration
When project created, do
```bash
cd project_name
```
and open `config` (`apps/project_name/config` if you did `--umbrella`) folder, and define database connection in `config :projet_name, ProjectName.Repo` block. By default, Phoenix provides connection like:
```elixir
username: "postgres",
password: "postgres",
database: "hello_world_dev",
hostname: "localhost"
```
So change it if your local settings is different.

## Starting up the server
Do just
```bash
mix ecto.create
```
to connect to database and 
```bash
mix phx.server
```
to start your local server.

Congratulations! You can see result at `http://localhost:4000`