# Piral Micro Frontend Project

## Setup Process

### Prerequisites
- Make sure you have Node.js installed, preferably version v10 or later.

### Setting up the Tooling
1. Install the Piral CLI globally:
   ```bash
   npm i piral-cli -g
   ```

2. Check the version of the Piral CLI:
   ```bash
   piral --version
   ```

### Create an Application Shell (Piral Instance)
#### Scaffold an application shell
```bash
piral new --target my-app
```

#### Run the Application Shell
Start the Piral instance in debug mode:
```bash
npx piral debug
```

### Create Package for the Application Shell
To use the Piral instance as the app shell, create an npm package:
```bash
npx piral build
```

### Create Pilet using the Piral CLI
A pilet is a module that can be dynamically loaded into the Piral instance.

#### Create Pilet
Scaffold a new pilet with the name 'my-pilet' for the app shell 'my-app':
```bash
pilet new ./my-app/dist/emulator/my-app-1.0.0.tgz --target my-pilet
```

#### Start the Pilet
Start a Pilet in debug mode:
```bash
npx pilet debug
```

### Publishing Pilets

#### Piral Cloud Services
Visit [Piral Cloud Services](https://portal.piral.cloud/) and sign up with Microsoft.

1. **Creating a Feed in the feed service:**
   - Follow the steps on the portal.

2. **Create an API Key required for publishing the pilet:**
   - Generate an API key on the portal.

3. **Publishing a Pilet to the Feed Service:**
   ```bash
   npx pilet publish --fresh --url https://feed.piral.cloud/api/v1/pilet/my-tutorial-feed --api-key <your-api-key>
   ```

4. **Configure the Piral Instance:**
   Update your Piral instance to fetch pilets from the feed service.
   ```javascript
   const feedUrl = 'https://feed.piral.cloud/api/v1/pilet/my-tutorial-feed';
   ```

Now you have successfully set up your Piral micro frontend project! Feel free to reach out if you have any questions.