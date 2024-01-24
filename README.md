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
    - Create New Feed
    ![Alt text](<Screenshot from 2024-01-24 12-14-02.png>)
    ![Alt text](<Screenshot from 2024-01-24 12-20-11.png>)
    
    - Now You can upload Micro-Frontend or CLI to publish Your Micro-Frontend
    ![Alt text](<Screenshot from 2024-01-24 12-22-49.png>)

    - Manage API key by Generating New API
    ![Alt text](<Screenshot from 2024-01-24 12-23-15.png>)

2. **Create an API Key required for publishing the pilet:**
   - Generate an API key on the portal.
    ![Alt text](<Screenshot from 2024-01-24 12-24-04.png>)
    ![Alt text](<Screenshot from 2024-01-24 12-25-04.png>)

   - Successfully Generate API key 
    ![Alt text](<Screenshot from 2024-01-24 12-25-24.png>)
3. **Publishing a Pilet to the Feed Service:**
   ```bash
   npx pilet publish --fresh --url https://feed.piral.cloud/api/v1/pilet/my-feed-name --api-key <your-api-key>
   ```

4. **Configure the Piral Instance:**
   Update your Piral instance to fetch pilets from the feed service.
   ```javascript
   const feedUrl = 'https://feed.piral.cloud/api/v1/pilet/my-feed-name';
   ```

   ## Disadvantage
   - The framework may incur costs after a certain number of published pilets, which could impact developers on a budget or smaller projects.