# Running Node.js with PM2 in Production Mode

To run your Node.js application in production mode using PM2 with the `npm run prod` command, use:

```bash
pm2 start npm --name "your-app-name" -- run prod
```

## Command Breakdown

- `pm2 start npm`: Tells PM2 to start an npm process
- `--name "your-app-name"`: Sets a custom name for your PM2 process (replace "your-app-name" with your desired name)
- `-- run prod`: Passes the `run prod` arguments to npm, which will execute the `prod` script defined in your package.json

> **Note**: Make sure you have PM2 installed globally on your system before running this command.