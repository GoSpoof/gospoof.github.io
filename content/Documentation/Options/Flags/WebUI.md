---
title: WebUI (--WebUI)
---
The WebUI flag launches the GoSpoof Command Center, providing a graphical interface for monitoring and managing GoSpoof.

## Usage

```bash
./goSpoof -WebUI
```

## Description

- No default value
- Launches web-based Command Center interface
- Provides visual monitoring and management
- Accessible at http://localhost:3000

## Accessing the WebUI

When launched with the `--WebUI` flag, the Command Center is accessible at:
```
http://localhost:3000
```

## Running WebUI Independently

You can also run the WebUI without the full GoSpoof tool:

1. Navigate to the Web/Server directory:
```bash
cd Web/Server
```

2. Start the server:
```bash
node server.js
```

3. Access the interface at `http://localhost:3000`

[[Documentation/Options/Options overview|Back to Options Overview]]
    