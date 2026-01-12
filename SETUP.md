# Setup Instructions for Explore Hut

## Quick Start

### 1. Install Dependencies
```bash
npm install
```

### 2. Create `.env` File

Create a `.env` file in the project root directory with the following variables:

```env
# MongoDB Atlas Database Connection URL
# Get this from: https://www.mongodb.com/atlas
ATLAS_DB_URL=mongodb+srv://username:password@cluster.mongodb.net/database_name?retryWrites=true&w=majority

# Session Secret (use a random string for security)
# Generate a random string, e.g., use: node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
SECRET=your-secret-key-here-change-this-to-random-string

# Cloudinary Configuration (for image uploads)
# Get these from: https://cloudinary.com/users/register_free
CLOUD_NAME=your-cloudinary-cloud-name
CLOUD_API_KEY=your-cloudinary-api-key
CLOUD_API_SECRET=your-cloudinary-api-secret
```

### 3. Get Your Credentials

#### MongoDB Atlas:
1. Sign up at [MongoDB Atlas](https://www.mongodb.com/atlas)
2. Create a free cluster
3. Create a database user
4. Whitelist your IP address (or use 0.0.0.0/0 for development)
5. Get your connection string from "Connect" → "Connect your application"

#### Cloudinary:
1. Sign up at [Cloudinary](https://cloudinary.com/users/register_free)
2. Go to Dashboard
3. Copy your `Cloud Name`, `API Key`, and `API Secret`

#### Generate a Secret:
Run this command to generate a random secret:
```bash
node -e "console.log(require('crypto').randomBytes(32).toString('hex'))"
```

### 4. Run the Application

For development (with auto-reload):
```bash
npm run dev
```

For production:
```bash
npm start
```

### 5. Access the Application

Open your browser and navigate to:
```
http://localhost:8080
```

## Troubleshooting

### App crashes on startup
- Make sure you have created the `.env` file
- Verify all environment variables are set correctly
- Check that your MongoDB Atlas connection string is correct
- Ensure your IP is whitelisted in MongoDB Atlas

### Database connection fails
- Verify your `ATLAS_DB_URL` is correct
- Check your MongoDB Atlas cluster is running
- Ensure your IP address is whitelisted
- Verify your database username and password are correct

### Session errors
- Make sure `SECRET` is set in your `.env` file
- The secret should be a random string (use the command above to generate one)
