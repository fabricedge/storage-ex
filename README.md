# Supabase Storage

[Storage](https://supabase.com/docs/guides/storage) implementation for the [Supabase Potion](https://hexdocs.pm/supabase_potion) SDK in Elixir.

## Installation

```elixir
def deps do
  [
    {:supabase_potion, "~> 0.6"},
    {:supabase_storage, "~> 0.4.2"} # x-release-please-version
  ]
end
```

## Usage

Firstly you need to initialize your Supabase client(s) as can be found on the [Supabase Potion documentation](https://hexdocs.pm/supabase_potion/readme.html#usage)

Now you can pass the Client to the `Supabase.Storage` functions:

```elixir
iex> Supabase.Storage.list_buckets(%Supabase.Client{})
```

## Upload File inside bucket
Secret Key : https://supabase.com/dashboard/project/[YOUR-PROJECT]/settings/api-keys/new
<img width="600" height="550" alt="image" src="https://github.com/user-attachments/assets/8c74e441-909d-4644-b864-8cad72dbef14" />
URL: https://supabase.com/dashboard/project/[YOUR-PROJECT]/settings/api


```elixir
iex> {:ok, client} = Myapp.Supabase.Client.get_client()
iex> storage= Supabase.Storage.from(client, "yourbucket")
iex> Supabase.Storage.File.upload(storage, "/file/path/local/file.jpg", "/folder/images/file.jpg")
```
