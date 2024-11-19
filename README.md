
# URL Shortener

This is a **URL Shortener** project implemented in **Golang**. It provides a fast and efficient way to shorten long URLs into compact, shareable links. The application preprocesses URLs and handles requests to return the original URLs for shortened links.

## Features

- Shorten long URLs into unique, compact links.
- Retrieve the original URL from a shortened link.
- Efficient preprocessing to ensure URL validation and uniqueness.
- High performance, leveraging Golang's simplicity and concurrency capabilities.

## Installation

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/<your-username>/url-shortener.git
   cd url-shortener
   ```

2. **Install Dependencies**  
   Make sure you have Go installed. If not, download and install it from [Go's official site](https://golang.org/dl/).  
   Then, install dependencies:
   ```bash
   go mod tidy
   ```

3. **Run the Application**  
   ```bash
   go run main.go
   ```

## Usage

### Shorten a URL
Send a POST request to `/shorten` with the following JSON payload:
```json
{
  "url": "https://example.com/some-long-url"
}
```

**Response:**
```json
{
  "short_url": "http://localhost:8080/abcd123"
}
```

### Retrieve the Original URL
Send a GET request to the shortened URL path (e.g., `/abcd123`).  
**Response:**
- Redirects to the original URL.

### API Endpoints
- `POST /shorten`: Accepts a JSON payload with a URL and returns the shortened URL.
- `GET /<short_code>`: Redirects to the original URL associated with the short code.

## Configuration

The application settings can be customized through environment variables:
- `PORT`: The port on which the server will run. Default is `8080`.
- `BASE_URL`: The base URL for shortened links. Default is `http://localhost:8080`.

## Project Structure

```
url-shortener/
├── main.go             # Entry point of the application
├── handlers/           # API endpoint logic
├── services/           # Core logic for URL shortening
├── storage/            # In-memory or persistent storage implementation
├── utils/              # Helper functions and utilities
└── README.md           # Project documentation
```

## Contribution

Contributions are welcome! To contribute:
1. Fork the repository.
2. Create a new branch: `git checkout -b feature-name`.
3. Commit your changes: `git commit -m "Add feature"`.
4. Push to the branch: `git push origin feature-name`.
5. Open a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

---

Happy shortening! 🚀
