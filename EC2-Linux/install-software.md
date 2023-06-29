# Login as root
sudo su

# Update software
sudo yum update -y

# Install software
sudo yum install httpd -y
sudo service httpd start
sudo systemctl enable httpd

cd /var/www/html
sudo vi index.html
# Copy some HTML sample on the internet then paste here
# Save index.html file


# Install node, npm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
. ~/.nvm/nvm.sh
nvm install 16
node -e "console.log('Running Node.js ' + process.version)"