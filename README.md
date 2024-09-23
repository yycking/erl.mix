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
4. run iex
   ```console
   $ iex -S mix
   Erlang/OTP 27 [erts-15.1] [source] [64-bit] [smp:8:8] [ds:8:8:10] [async-threads:1] [jit] [dtrace]
   
   Compiling 1 file (.erl)
   Generated erlample app
   Interactive Elixir (1.17.3) - press Ctrl+C to exit (type h() ENTER for help)
   iex(1)> :erlample.hello()
   :world
   ```
5. edit test file `test/example_test.exs`
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
 6. run test
   ```console
   $ mix test
   Running ExUnit with seed: 79742, max_cases: 16

   ..
   Finished in 0.01 seconds (0.00s async, 0.01s sync)
   1 doctest, 1 test, 0 failures
   ```
   
