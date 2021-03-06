# Ping

Checking the Health of Your Traefik Instances
{: .subtitle }

## Configuration Examples

??? example "Enabling /ping"

    ```toml
    [ping]
    ```

??? example "Enabling /ping on a dedicated EntryPoint"
    
    ```toml
    [entrypoints]
      [entrypoints.web]
        address = ":80"
      
      [entrypoints.ping]
        address = ":8082"
    
    [ping]
        entryPoint = "ping"
    ```

| Path    | Method        | Description                                                                                         |
|---------|---------------|-----------------------------------------------------------------------------------------------------|
| `/ping` | `GET`, `HEAD` | A simple endpoint to check for Traefik process liveness. Return a code `200` with the content: `OK` |

## Configuration Options

The `/ping` health-check URL is enabled with the command-line `--ping` or config file option `[ping]`.

You can customize the `entryPoint` where the `/ping` is active with the `entryPoint` option (default value: `traefik`)