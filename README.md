# Westside Rising - Community Website

A modern, responsive website for the Westside Rising nonprofit organization, featuring a comprehensive event management system with role-based admin access.

## 🌟 Features

### Public Features
- **Modern Responsive Design** - Beautiful, mobile-first design following Westside Rising's community-focused theme
- **Community Information** - About section highlighting community organizing, capacity building, and civic engagement
- **Programs & Initiatives** - Showcase of leadership development, community organizing, and youth engagement programs
- **Events Display** - Public listing of upcoming community events
- **Get Involved Section** - Multiple ways for community members to participate
- **Contact Information** - Easy way for community members to reach out

### Admin Features
- **Code-Based Authentication** - Secure access using unique admin codes (no traditional login required)
- **Two-Tier Admin System**:
  - **Main Administrator** - Full access to all features
  - **Sub-Administrators** - Limited access to their own events only
- **Event Management**:
  - Add new events with title, description, date, time, location, and image
  - Delete events (main admin can delete any event, sub-admins only their own)
  - View event attribution (who created each event)
- **Admin Code Management** (Main Admin Only):
  - Generate unique access codes for sub-administrators
  - Delete sub-admin codes to revoke access
  - View all active admin codes and their creation dates

## 🚀 Getting Started

### Prerequisites
- Node.js (v14 or higher)
- npm

### Installation

1. Clone this repository
```bash
git clone https://github.com/Ohlluu/wr.git
cd wr
```

2. Install dependencies
```bash
npm install
```

3. Start the development server
```bash
npm start
```

4. Open your browser and navigate to `http://localhost:3000`

## 🔐 Admin Access

### Default Main Admin Access
- **Code**: `MAIN_ADMIN_2024`
- **Role**: Main Administrator
- **Permissions**: Full access to all features

### Using Admin Panel

1. Click the "Admin" button in the navigation
2. Enter your admin code
3. Access the admin panel to:
   - **Manage Events**: Add new events, delete existing events
   - **Manage Codes** (Main Admin only): Create codes for sub-admins, delete existing codes

### Creating Sub-Admin Codes

1. Log in as main admin
2. Go to "Manage Codes" tab
3. Click "Create New Code"
4. Enter the sub-admin's name
5. Share the generated code with the sub-admin

## 🎨 Design & Theme

### Color Scheme
- **Primary Green** (#2D5F3F) - Representing growth and community
- **Secondary Orange** (#E67E22) - Representing energy and engagement
- **Accent Blue** (#3498DB) - Representing hope and trust
- **Background Cream** (#FDFBF7) - Warm, welcoming background
- **Text Charcoal** (#2C3E50) - Clean, readable text

### Typography
- **Font Family**: Inter (Google Fonts)
- **Modern, clean sans-serif** design for excellent readability
- **Weighted appropriately** for headings, body text, and UI elements

## 📱 Responsive Design

The website is fully responsive and optimized for:
- **Desktop** (1200px+)
- **Tablet** (768px - 1199px)
- **Mobile** (320px - 767px)

## 🗄️ Database Structure

The application uses SQLite with the following tables:

### admin_codes
- `id` - Primary key
- `code` - Unique admin access code
- `sub_admin_name` - Name of the sub-administrator
- `created_at` - Timestamp of code creation
- `is_main_admin` - Boolean flag for main admin privileges

### events
- `id` - Primary key
- `title` - Event title
- `description` - Event description
- `date` - Event date
- `time` - Event time (optional)
- `location` - Event location (optional)
- `image_url` - Event image URL (optional)
- `created_by_code` - Admin code of creator
- `created_by_name` - Name of creator
- `created_at` - Timestamp of event creation

## 🛠️ API Endpoints

### Authentication
- `POST /api/verify-code` - Verify admin code

### Events
- `GET /api/events` - Get all events
- `POST /api/events` - Create new event
- `DELETE /api/events/:id` - Delete event

### Admin Codes (Main Admin Only)
- `GET /api/admin-codes` - Get all admin codes
- `POST /api/admin-codes` - Create new admin code
- `DELETE /api/admin-codes/:code` - Delete admin code

## 🔒 Security Features

- **Code-based authentication** - No passwords to compromise
- **Role-based permissions** - Sub-admins can only manage their own events
- **SQL injection protection** - Parameterized queries
- **Input validation** - Server-side validation of all inputs
- **CORS protection** - Configured for secure API access

## 📁 Project Structure

```
wr/
├── public/
│   ├── css/
│   │   └── styles.css          # Modern CSS styling
│   ├── js/
│   │   └── script.js           # Client-side JavaScript
│   ├── images/
│   │   └── placeholder.txt     # Image directory
│   └── index.html              # Main HTML file
├── server.js                   # Express.js server
├── package.json               # NPM dependencies
├── westside_rising.db         # SQLite database (created on first run)
└── README.md                  # This file
```

## 🌐 Deployment

### Production Deployment Steps:

1. **Prepare environment**:
   - Set `NODE_ENV=production`
   - Set `PORT` environment variable if needed

2. **Database**:
   - The SQLite database will be created automatically
   - Ensure the server has write permissions to the directory

3. **Static assets**:
   - All frontend assets are served from the `public/` directory
   - Add actual images to `public/images/` directory

4. **Security**:
   - Change the default main admin code in production
   - Consider using environment variables for sensitive configuration

### Environment Variables (Optional)
- `PORT` - Server port (default: 3000)
- `NODE_ENV` - Environment mode

## 🧪 Testing

To test the application:

1. **Start the server**: `npm start`
2. **Access the website**: Navigate to `http://localhost:3000`
3. **Test public features**: Browse all sections of the website
4. **Test admin functionality**:
   - Click "Admin" button
   - Use code `MAIN_ADMIN_2024`
   - Test event creation/deletion
   - Test sub-admin code creation (if main admin)

## 🤝 Contributing

This website was designed specifically for Westside Rising's community organizing mission. The design reflects their values of:
- Community empowerment
- Civic engagement
- Collaborative leadership
- Neighborhood development

## 📧 Support

For technical support or questions about the admin system, please contact the development team.

---

**Built with ❤️ for the Westside Rising community**