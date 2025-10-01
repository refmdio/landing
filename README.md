# RefMD Landing Page

This directory contains the static assets for the RefMD SaaS introduction page. Serve `index.html` with its accompanying `styles.css` via your web server (e.g. Caddy) before proxying other routes to the authenticated app.

Example Caddy snippet:

```
example.com {
    handle / {
        root * /path/to/refmd/landing
        file_server
    }

    handle /auth* {
        reverse_proxy 127.0.0.1:3000
    }

    handle /* {
        reverse_proxy 127.0.0.1:3000
    }
}
```

Replace `/path/to/refmd/landing` with the absolute path to this directory and adjust upstream addresses for your deployment.
