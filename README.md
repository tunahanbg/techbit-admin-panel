# TechBit Admin Panel

A role-based administration panel for the TechBit startup.

## Features

* User authentication with PostgreSQL
* Role-based access control (admin, devops, developer, documentation)
* User management (admin)
* Service access and management

## Installation

### Requirements

* Docker and Docker Compose
* Node.js (for local development)

### Docker Setup

1. Clone the project:
```
   git clone https://github.com/your-username/techbit-admin.git
   cd techbit-admin
```
2. Start with Docker Compose:
```
   docker-compose up -d
```
3. Navigate to `http://localhost:3000` in your browser.

### Nginx Setup

1. Copy the Nginx configuration file to `/etc/nginx/sites-available/`:
```
   sudo cp nginx.conf /etc/nginx/sites-available/techbit
```
2. Enable the site:
```
   sudo ln -s /etc/nginx/sites-available/techbit /etc/nginx/sites-enabled/
```
3. Test the Nginx configuration:
```
   sudo nginx -t
```
4. Restart Nginx:
```
   sudo systemctl restart nginx
```
5. Navigate to `http://techbit.local` in your browser (or the domain specified in the configuration).

## Usage

### Default Users

The following users are predefined in the system:

* **Admin**: yaltay / password123
* **DevOps**: tbuyukgebiz / password123
* **Developer**: ngok / password123
* **Documentation**: egenc / password123

### Services

The following services are accessible based on user roles:

* GitLab (Code Management & CI/CD)
* DokuWiki (Documentation)
* PostgreSQL (Database)
* Nagios and Munin (Monitoring)
* Email (Postfix & Dovecot)
* Etherpad (Collaborative Text Editor)
* Elastic (Search)
* Portainer (Container Management)

## Development

1. Install dependencies:
```
   npm install
```
2. Start in development mode:
```
   npm run dev
```

## PostgreSQL Database

To access the PostgreSQL database:
```
psql -h localhost -U techbit -d techbit_db
```

Default password: `techbit123`

## License

MIT
