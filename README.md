# URL Shortener

This is a simple URL shortener server written in Go. It supports redirection based on a predefined set of URL mappings provided via a map or YAML configuration.

## Overview

The server listens on port `8080` and redirects requests based on predefined paths. It uses the `github.com/gophercises/urlshort` package to handle URL shortening.

## Features

- Redirects based on a map of paths to URLs
- Supports YAML configuration for path-URL mappings
- Provides a default handler for unmatched paths

## Installation

1. Clone the repository
   ```sh
   git clone https://github.com/yourusername/urlshortener
   ```
2. Navigate to the project directory
   ```sh
   cd urlshortener
   ```
3. Install dependencies
   ```sh
   go get -u github.com/gophercises/urlshort
   go get -u gopkg.in/yaml.v2
   ```

## Usage

1. Run the server
   ```sh
   go run main.go
   ```
2. Open your browser and navigate to `http://localhost:8080`

## URL Mappings

The URL mappings are defined in two ways:

1. **Map Handler**: A map of paths to URLs defined in the `main` function.
   ```go
   pathsToUrls := map[string]string{
       "/urlshort-godoc": "https://godoc.org/github.com/gophercises/urlshort",
       "/yaml-godoc":     "https://godoc.org/gopkg.in/yaml.v2",
   }
   ```

2. **YAML Handler**: A YAML configuration string defined in the `main` function.
   ```yaml
   - path: /urlshort
     url: https://github.com/gophercises/urlshort
   - path: /urlshort-final
     url: https://github.com/gophercises/urlshort/tree/solution
   ```

## Default Handler

If a path does not match any of the predefined mappings, the default handler will respond with a simple "Hello, world!" message.

## Example

Once the server is running, you can test the URL shortener by visiting the following URLs:

- `http://localhost:8080/urlshort-godoc` will redirect to `https://godoc.org/github.com/gophercises/urlshort`
- `http://localhost:8080/urlshort` will redirect to `https://github.com/gophercises/urlshort`

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
