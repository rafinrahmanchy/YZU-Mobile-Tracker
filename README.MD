# 📱 Mobile Tracking System

A comprehensive Django-based mobile device tracking system that enables users to monitor and manage multiple mobile devices with real-time location tracking capabilities.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-5.2.8-green.svg)](https://www.djangoproject.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📋 Table of Contents

- [Features](#-features)
- [System Requirements](#-system-requirements)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Technology Stack](#-technology-stack)
- [Configuration](#-configuration)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### 🔐 User Authentication & Management
- **User Registration**: Secure account creation with password validation
- **User Login/Logout**: Session-based authentication system
- **User Dashboard**: Personalized dashboard displaying all registered devices
- **Profile Management**: View and manage user profile information

### 📱 Device Management
- **Device Registration**: Add multiple devices with unique device IDs (auto-generated)
- **Device List View**: Display all devices associated with the user account
- **Device Settings**: Configure tracking intervals and device preferences
- **Device Status Monitoring**: Track active/inactive device states

### 🌍 Location Tracking
- **Real-time Location Updates**: Add and store GPS coordinates with timestamps
- **Live Map View**: Interactive map displaying current locations of all tracked devices
- **Location History**: View historical location data for each device
- **Speed & Accuracy Tracking**: Record device speed and GPS accuracy
- **Online/Offline Status**: Monitor device connectivity status

### 🎨 User Interface
- **Responsive Design**: Mobile-friendly interface
- **Modern Admin Panel**: Enhanced admin interface with Django Jazzmin
- **Interactive Maps**: Visual representation of device locations
- **Message Notifications**: Success/error message feedback system

### 🔧 Additional Features
- **SQLite Database**: Lightweight, file-based database storage
- **Automatic Timestamps**: Track when location data was recorded
- **User-Device Relationship**: Each device is linked to a specific user
- **Configurable Tracking Intervals**: Set custom tracking frequencies per device

## 💻 System Requirements

### Prerequisites

- **Python**: 3.8 or higher
- **pip**: Python package installer
- **Git**: Version control system (for cloning the repository)

### Operating System Support

- ✅ Windows 10/11
- ✅ macOS 10.14+
- ✅ Linux (Ubuntu 18.04+, Debian, Fedora, etc.)

### Hardware Requirements

- **RAM**: Minimum 2GB (4GB recommended)
- **Storage**: At least 500MB free space
- **Network**: Internet connection for initial setup and package installation

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/Mobile_tracking.git
cd Mobile_tracking
```

### 2. Create Virtual Environment

**Windows:**
```bash
python -m venv myenv
myenv\Scripts\activate
```

**macOS/Linux:**
```bash
python3 -m venv myenv
source myenv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

The following packages will be installed:
- `Django==5.2.8` - Web framework
- `django-jazzmin==3.0.1` - Modern admin interface
- `asgiref==3.11.0` - ASGI specification
- `sqlparse==0.5.3` - SQL parser
- `tzdata==2025.2` - Timezone database

### 4. Database Setup

Run migrations to create the database schema:

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Create Superuser (Optional)

Create an admin account to access the Django admin panel:

```bash
python manage.py createsuperuser
```

Follow the prompts to set username, email, and password.

### 6. Run Development Server

```bash
python manage.py runserver
```

The application will be available at `http://127.0.0.1:8000/`

## 📖 Usage

### First Time Setup

1. **Access the Application**: Open your browser and navigate to `http://127.0.0.1:8000/`

2. **Register an Account**: Click on the registration link and create a new user account

3. **Login**: Use your credentials to log into the system

### Managing Devices

#### Adding a New Device

1. Navigate to **Dashboard** → **Add Device**
2. Enter device details:
   - Device name
   - Tracking interval (in seconds)
   - Toggle tracking status
3. Click **Save** - a unique device ID will be auto-generated

#### Viewing Devices

- Access the **Device List** from the dashboard
- View all registered devices with their current status
- Click on any device to modify settings

### Tracking Locations

#### Adding Location Data

1. Navigate to **Add Location Data**
2. Select the device from the dropdown
3. Enter location details:
   - Latitude
   - Longitude
   - Speed (optional)
   - GPS Accuracy (optional)
4. Submit the form

#### Viewing Live Map

- Click on **Live Map** from the navigation menu
- See real-time locations of all your tracked devices
- Interactive markers show device positions

#### Viewing Location History

1. Go to **Device List**
2. Click on a specific device
3. Select **Location History**
4. Browse through historical tracking data with timestamps

### Admin Panel

Access the enhanced admin interface at `http://127.0.0.1:8000/admin/`

- Manage users, devices, and location data
- View comprehensive system statistics
- Perform bulk operations

## 📁 Project Structure

```
Mobile_tracking/
│
├── tracking_system/          # Main project configuration
│   ├── settings.py           # Project settings
│   ├── urls.py              # Root URL configuration
│   ├── wsgi.py              # WSGI configuration
│   └── asgi.py              # ASGI configuration
│
├── users/                    # User authentication app
│   ├── models.py            # CustomUser model
│   ├── views.py             # Login, register, dashboard views
│   ├── forms.py             # User registration forms
│   ├── urls.py              # User-related URLs
│   └── admin.py             # User admin configuration
│
├── devices/                  # Device management app
│   ├── models.py            # Device model
│   ├── views.py             # Device CRUD operations
│   ├── forms.py             # Device forms
│   ├── urls.py              # Device-related URLs
│   └── admin.py             # Device admin configuration
│
├── tracking/                 # Location tracking app
│   ├── models.py            # LocationData model
│   ├── views.py             # Tracking views (map, history)
│   ├── urls.py              # Tracking-related URLs
│   └── admin.py             # Tracking admin configuration
│
├── templates/                # HTML templates
│   ├── base.html            # Base template
│   ├── users/               # User-related templates
│   ├── devices/             # Device-related templates
│   └── tracking/            # Tracking-related templates
│
├── manage.py                 # Django management script
├── requirements.txt          # Python dependencies
├── run.bat                   # Git automation script (Windows)
├── db.sqlite3               # SQLite database
└── .gitignore               # Git ignore rules
```

## 🛠️ Technology Stack

### Backend
- **Django 5.2.8**: High-level Python web framework
- **Python 3.8+**: Core programming language
- **SQLite**: Lightweight relational database

### Frontend
- **HTML5**: Markup language
- **CSS3**: Styling
- **JavaScript**: Client-side interactivity

### Admin Interface
- **Django Jazzmin**: Modern and responsive admin theme

### Additional Tools
- **Git**: Version control
- **pip**: Package management

## ⚙️ Configuration

### Database Configuration

The project uses SQLite by default. To change to another database (e.g., PostgreSQL, MySQL):

Edit `tracking_system/settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_db_name',
        'USER': 'your_db_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

### Security Settings

For production deployment, update these settings in `settings.py`:

```python
DEBUG = False
SECRET_KEY = 'your-secure-secret-key'
ALLOWED_HOSTS = ['yourdomain.com', 'www.yourdomain.com']
```

### Timezone Configuration

Change timezone in `settings.py`:

```python
TIME_ZONE = 'America/New_York'  # Change to your timezone
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/YourFeatureName
   ```
3. **Commit your changes**
   ```bash
   git commit -m "Add some feature"
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/YourFeatureName
   ```
5. **Open a Pull Request**

### Code Style Guidelines

- Follow PEP 8 for Python code
- Use meaningful variable and function names
- Add comments for complex logic
- Update documentation when adding features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Authors

- **Your Name** - *Initial work*

## 🙏 Acknowledgments

- Django Software Foundation for the amazing framework
- Django Jazzmin for the beautiful admin interface
- All contributors who help improve this project

## 📞 Support

For support, questions, or feature requests:
- Open an issue on GitHub
- Contact: your.email@example.com

---

**Made with ❤️ using Django**
