# Live World News - Real-Time News Dashboard

A modern, real-time news aggregation application built with Electron, Express, React, and MongoDB.

## Features

✅ **Real-time News Updates** - Live news from multiple sources (BBC, Reuters, NY Times, Al Jazeera, The Guardian)
✅ **Offline Support** - Read saved articles without internet connection
✅ **User Authentication** - Secure JWT-based authentication
✅ **Article Management** - Create, edit, publish, and archive articles
✅ **Category Management** - Organize news by categories
✅ **User Profiles** - Manage user profiles and reading history
✅ **Social Features** - Like and comment on articles
✅ **Admin Dashboard** - Statistics and user management
✅ **Responsive Design** - Works on desktop and tablet

## Tech Stack

### Frontend
- React.js
- Modern CSS3
- Responsive Grid Layout

### Desktop
- Electron
- Node.js

### Backend
- Express.js
- MongoDB with Mongoose
- JWT Authentication
- bcryptjs for password encryption

### DevOps
- CORS enabled
- Helmet.js for security
- Rate limiting
- File upload handling

## Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/benchiri/benchiri581.git
cd benchiri581
```

2. **Install dependencies**
```bash
npm install
```

3. **Environment Configuration**

Create a `.env` file in the root directory with your configuration:

```
PORT=5000
NODE_ENV=development
MONGODB_URI=mongodb://localhost:27017/newsdb
JWT_SECRET=your_secret_key_here
JWT_EXPIRE=7d
REACT_APP_API_URL=http://localhost:5000
```

For MongoDB Atlas (cloud), use:
```
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/newsdb
```

4. **Start the application**

For development (with both React and Electron):
```bash
npm run dev
```

Or run them separately:
```bash
# Terminal 1: Start React dev server
npm run start-react

# Terminal 2: Start Electron
npm start
```

For backend only:
```bash
npm run server
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user (protected)

### Articles
- `GET /api/articles` - Get all published articles
- `GET /api/articles/:slug` - Get single article
- `POST /api/articles` - Create article (editor/admin)
- `PUT /api/articles/:id` - Update article (editor/admin)
- `DELETE /api/articles/:id` - Delete article (admin)
- `POST /api/articles/:id/like` - Like article
- `POST /api/articles/:id/comments` - Add comment
- `POST /api/articles/:id/save` - Save article

### Categories
- `GET /api/categories` - Get all categories
- `GET /api/categories/:slug` - Get category with articles
- `POST /api/categories` - Create category (admin)
- `PUT /api/categories/:id` - Update category (admin)
- `DELETE /api/categories/:id` - Delete category (admin)

### Users
- `GET /api/users/:id` - Get user profile
- `PUT /api/users/profile` - Update profile (protected)
- `GET /api/users/saved/articles` - Get saved articles (protected)

### Admin
- `GET /api/admin/stats` - Get statistics (admin)
- `GET /api/admin/users` - Get all users (admin)
- `PUT /api/admin/users/:id/role` - Update user role (admin)

## File Structure

```
benchiri581/
├── main.js                 # Electron main process + Express backend
├── package.json           # Dependencies and scripts
├── .env                   # Environment variables (keep private!)
├── README.md              # This file
└── uploads/               # User uploaded files (auto-created)
    ├── articles/          # Article images
    └── avatars/           # User avatars
```

## Security Features

🔒 **Password Encryption** - bcryptjs
🔒 **JWT Authentication** - Secure token-based auth
🔒 **CORS Protection** - Cross-origin requests controlled
🔒 **Helmet.js** - HTTP security headers
🔒 **Rate Limiting** - Prevent abuse
🔒 **Context Isolation** - Electron security

## Default Roles

- **user** - Can read articles, like, comment, save
- **editor** - Can create and edit articles
- **admin** - Full access to all features

## Troubleshooting

### MongoDB Connection Error
```
Make sure MongoDB is running:
mongod
```

### Port Already in Use
```
Change PORT in .env:
PORT=5001
```

### Electron Not Loading
```
Make sure React dev server is running:
npm run start-react
```

### Module Not Found
```
Delete node_modules and reinstall:
rm -rf node_modules
npm install
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - feel free to use this project for personal or commercial purposes.

## Support

For issues and questions, please open an issue on GitHub.

---

**Made with ❤️ by Benchiri**
