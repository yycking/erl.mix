# erl.mix
create Erlang from mix

1. `mix new example`
2. edit file `mix.exs`
   change `elixir: "~> 1.17",` to
   ```elixir
   language: :erlang,
   erlc_paths: ["lib"],
   ```
3. rename `lib/example.ex` to `lib/example.erl`
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
5. edit file `test/example_test.exs`
   replace
   ```elixir
   defmodule ExampleTest do
       use ExUnit.Case
   
       doctest :example
   
       test "greets the world" do
          assert :example.hello() == :world
       end
   end
   ```
   
