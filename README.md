# erl.mix
create Erlang from mix

1. `mix new example`
2. edit file `mix.ext`
   change `elixir: "~> 1.17",` to
   ```elixir
   language: :erlang,
   erlc_paths: ["lib"],
   ```
3. rename `example.ex` to `example.erl`
   replace code with
   ```erlang
   -module(example).
   -export([hello/0]).

   %% Documentation
   %% Hello world.
   %%
   %% Examples:
   %%     1> :erlample.hello()
   %%     world.

   hello() ->
       world.
   ```
4. run
   1. `iex -S mix`
   2. `:erlample.hello()`
   
