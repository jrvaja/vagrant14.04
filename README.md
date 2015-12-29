# vagrant14.04
<h2>Step 1 : Watch Video at Laracast</h2>
<a href='https://laracasts.com/lessons/get-off-mamp-now'>Get Off MAMP </a>

<h2>Step 2 : Install Virtual box and Vagrant </h2>
1.<a href='https://www.virtualbox.org/'>Virtual Box</a> <br>
2.<a href='https://www.vagrantup.com'>Vagrant</a>

Select a folder for your develpment code.

<h2>Step 3: Add the Alias</h2>
Add the below alias to your <i>~/.bashrc</i> file or <i>~/.bash_profile</i>
<br>
```
alias lamp="curl -L -o 'install.sh' https://goo.gl/xQR4ud && curl -L -o 'Vagrantfile' https://goo.gl/TMPyh2 && vagrant up"
```

Provide source to your ~/.bashrc file or ~/.bash_profile
Ex : source ~/.bashrc

<h2>Step 4: Install</h2>
cd to your desired directory in the Terminal, and run lamp to install your LAMP stack.

This will take a few minutes as your intenet connection.

<h2>Step 5: Done. Go Poke Around.</h2>
RUN <b>vagrant up </b> to start your virtual dev machine.

You can connet to ssh by the below command
<b>vagrant ssh</b>

Now, All is set.


If you cd to /vagrant, this folder will be shared with your project root on your local/host machine. That means, when you create a file on your Mac, it will instantly be shared (both ways) with the /vagrant directory on your VM. However, we're also syncing with the /var/wwwdirectory on your VM, which is the Apache root. That means, if you visit http://192.168.33.21, you should see "It Worked!" You can change the IP address in your Vagrantfile, if you need to.

Have fun! This also installs and enables X-Debug for you. You can stop using MAMP now.


<h2>Extra-1</h2>
Edit your hosts file to set a simpler address, like http://app.dev/.
```
sudo vi /etc/hosts
```
At the bottom of this file, add:

```
192.168.33.21 app.dev
```
Now, browse to ```http://app.dev.```

<h2>Extra-2</h2>
By default, Apache will set your document root to /var/www/html. If you don't want this...

```
$ vagrant ssh
$ sudo vim /etc/apache2/sites-available/000-default.conf
(Change `DocumentRoot /var/www/html` to `DocumentRoot /var/www`)
$ sudo service apache2 reload
```
Reload the browser. Now, your local project root will be treated as Apache's document root. Typically, though, you'll want to set Apache's document root to something like the public directory - so ``` DocumentRoot /var/www/public``` .

<h3>Extra-4: Multiple Websites With the Same VM</h3>
Maybe you want to run all of your sites and demos within this VM. Here's how.

For this example, maybe we're building a new app, called "Larabook." Begin by creating a new directory, "larabook" within the same directory that has the Vagrantfile that you pulled in during Step 3. Add a dummy index.php file here, just to prove that it's working.

```
$ vagrant ssh
$ cd /etc/apache2/sites-available/
$ sudo cp 000-default.conf larabook.conf
```
Open `larabook.conf, and set:
```
ServerName larabook.local
DocumentRoot /var/www/larabook
```


<h3>Extra-4</h3>
You don't have to for this example, but you'd probably want to add some additional config to this file - like:
```
<Directory /var/www/larabook>
  Options -Indexes +FollowSymLinks
  AllowOverride All
  Require all granted
</Directory>
```
Next, enable the new vhost, and reload Apache.

```
sudo a2ensite larabook
sudo service apache2 reload
```

<h2>For More Extra credits</h2>
Refer : <a href='https://gist.github.com/JeffreyWay/af0ee7311abfde3e3b73'> Gitgub Jeffrey Way</a>
``` The Killer feature of PHP ```

Enjoy development with PHP.

<h2>Power Command</h2>
Make an alias that points this your folder.
edit your :  ```source ~/.bashrc```

```
alias dev-up="cd ~/Code; vagrant up"
```
Get ssh rights to machine

```
alias dev-ssh="cd ~/Code; vagrant ssh"
```

you can add your custom aliases to make your work much easy.

Thanks to <a href='https://github.com/jeffreyway/'>Jeffrey Way</a>
