
# Learning and Exploring Drupal with Composer, Drush, and Docker

This project is an experimental setup designed to deepen familiarity with Drupal, focusing on core features, modules, theming, and deployment on Docker and Google Cloud Platform (GCP). 
 
## Prerequisites
- **Docker** and **Docker Compose** installed locally.
- **Google Cloud Platform** account (with Cloud Shell access).

## Project Setup
1. Cloning the Repository
Start by cloning this repository to your local environment:
git clone https://github.com/your-username/drupal-gov-cms.git
cd drupal-gov-cms

2. Setting Up Environment Variables
Create a .env file in the project’s root directory to manage sensitive or environment-specific information. Add variables such as:

![image](https://github.com/user-attachments/assets/251f40e9-4e76-4908-966f-f447bbef0df2)


### 1. Setting Up Composer

Composer is used to manage dependencies for Drupal and its modules:

1. **Install Composer Dependencies**:
   ```bash
   composer install
   ```
2. **Adding Modules and Themes**:

   - Install contributed modules like admin_toolbar:
       ```bash
       composer require drupal/admin_toolbar
        ```
   - Install contributed modules:
     ```bash
     composer require drupal/modulename
     ```
   - Enable core and contributed modules with Drush:
     ```bash
     ./vendor/bin/drush en modulename
     ```
![image](https://github.com/user-attachments/assets/23542621-84f2-41b6-9b73-d6c310663dbc)
 ![image](https://github.com/user-attachments/assets/b0628be1-77f7-460a-a275-ffa3806d8a0e)

 
### 2. Setting Up Drush

Drush is a command-line tool for Drupal management.

1. **Install Drush**:
   - If Drush isn’t already installed, add it via Composer:
     ```bash
     composer require drush/drush
     ```

2. **Using Drush Commands**:
I use** wsl -d Ubuntu** in windows system
![image](https://github.com/user-attachments/assets/dec9c82a-3313-4832-8bfa-a03c46502bdf)

   - Clear caches:
     ```bash
     ./vendor/bin/drush cache-rebuild
     ```
   - Update the database:
     ```bash
     ./vendor/bin/drush updatedb
     ```
   - Generate a sub-theme:
      ```bash
    ./vendor/bin/drush generate
      ```
## Managing Changes and Updates

1. **Pushing Updates to GitHub**:
   - Track changes and push them to the repository:
     ```bash
     git add .
     git commit -m "Descriptive message of changes"
     git push origin main
     ```

2. **Updating Drupal Core and Modules**:
   - Use Composer to update:
     ```bash
     composer update drupal/core --with-dependencies
     ```
### 3. Setting Up Docker and Docker Compose

Docker and Docker Compose allow us to break Drupal into separate containers (e.g., for web, database, etc.):

1. **Build and Start Containers**:
   - Use `docker-compose.yml` to configure services. Start them with:
     ```bash
     docker-compose up --build -d
     ```

2. **File Structure**:
   - The `docker-compose.yml` file is configured to create separate containers for the Drupal app and MySQL database. Optionally, `phpmyadmin` can be removed to simplify the setup.

### 6. Deploying on Google Cloud Platform (GCP)
![image](https://github.com/user-attachments/assets/dae70abd-d1ca-4ab9-ac44-04c4f3aaab13)

1. **Clone the Project to Google Cloud Shell**:
   - Open Google Cloud Console and clone the project:
     ```bash
     git clone https://github.com/xxx/drupal-gov-cms.git
     cd drupal-gov-cms
     ```

2. **Edit Environment Files for GCP**:
   - Update the `.env` file and `docker-compose.yml` as necessary for GCP configuration.

3. **Start Docker on GCP**:
   - Use Google Cloud Shell to start the containers:
     ```bash
     docker-compose up -d
     ```
![image](https://github.com/user-attachments/assets/c6b1d0bc-486e-46f9-971d-b0b7517c9cfc)

## Additional Notes

- **Customization**: Modify themes and configurations in `web/themes/` as needed.
- **Learning Resources**: [Explore the official Drupal, Composer, and Drush documentation for deeper insights into customizing and scaling your Drupal project.](https://www.youtube.com/watch?v=XJatVmC5-ro&t=577s)

 
