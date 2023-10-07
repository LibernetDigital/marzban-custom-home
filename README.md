# Marzban custom home page
### **Replace the green roller with your preferred website.**

> You must have marzban script installed. [Gozargah/Marzban](https://github.com/gozargah/marzban)

> This is not a theme or template for administration panel, it is a replacement for your IP/Domain without /dashboard


- Login to your marzban server using SSH and create the following directories using command below:
```
mkdir /var/lib/marzban/templates && mkdir /var/lib/marzban/templates/home
```
- Now head to the created directory and download the ```index.html``` file from this repository:
```
cd /var/lib/marzban/templates/home && wget https://raw.githubusercontent.com/LibernetDigital/marzban-custom-home/main/index.html
```
- now open the downloaded file using ```nano index.html```
- Go to the line 22 and change it to your preferred **TITLE**.
- And in line 23 replace the url with your preferred **WEBSITE URL**.
```
const title = "Independent";
const url = "https://www.independent.co.uk/";
```
> Some websites like **Google** doesn't let you embedding on your website.
- Save changes with ```CTRL + O``` and ```CTRL + X```.
- Then edit your ```.env``` file using command below:
```
nano /opt/marzban/.env
```
Uncomment below lines, save and exit:
```
# CUSTOM_TEMPLATES_DIRECTORY="/var/lib/marzban/templates/"
# HOME_PAGE_TEMPLATE="home/index.html"
```
to
```
CUSTOM_TEMPLATES_DIRECTORY="/var/lib/marzban/templates/"
HOME_PAGE_TEMPLATE="home/index.html"
```
- Now save .env file and restart marzban:
```
marzban restart
```
- Done, now you can open your marzban domain directly without /dashboard and see the changes. 
