# -Host-a-Web-Page-on-AWS-EC2-Using-Nginx-with-a-Custom-Port
Steps to Host a Website with Nginx
1. Stop Apache (if running)
If Apache is installed, stop and disable it to prevent conflicts with Nginx.

2. Install & Start Nginx
Install Nginx, start the service, and enable it to start on boot.

3. Modify Nginx Configuration
Update the Nginx configuration file to:

Change the document root from '
/usr/share/nginx/html to /var/www/html.

Set a custom listening port instead of the default (e.g., 90).

4. Create the Web Directory & Set Permissions
Ensure the correct directory structure and permissions:

Create /var/www/html if it doesn’t exist.

Assign ownership to the Nginx user.
Set appropriate file permissions.

Run the following commands:
sudo mkdir -p /var/www/html
sudo chown -R nginx:nginx /var/www/html
sudo chmod -R 755 /var/www/html

5. Move Website Files
Place the necessary website files (e.g., college.html) inside /var/www/html/.

6. Reload & Restart Nginx
Apply the changes and restart Nginx for the updates to take effect.

Run the following command:

sudo systemctl reload nginx

7. Update Security Group
Modify your AWS EC2 security group settings to allow incoming traffic on the chosen port (e.g., 90).

Access Your Website
Your website will be accessible at:

http://your-ec2-public-ip:90
