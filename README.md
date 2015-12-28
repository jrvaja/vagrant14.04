# vagrant14.04

Install Virtual box : <a href='https://www.virtualbox.org/'>Vagrant</a>
Ref : https://www.virtualbox.org/wiki/Downloads

Install <a href='https://www.vagrantup.com'>Vagrant</a>

Select a folder for your develpment code.

Add the below alias to your <i>~/.bashrc</i> file or <i>~/.bash_profile</i>
<br>
alias lamp="curl -L -o 'install.sh' https://goo.gl/xQR4ud && curl -L -o 'Vagrantfile' https://goo.gl/TMPyh2 && vagrant up"


Provide source to your ~/.bashrc file or ~/.bash_profile
Ex : source ~/.bashrc

This will take a few minutes as your intenet connection.

RUN <b>vagrant up </b> to start your virtual dev machine.

You can connet to ssh by the below command
<b>vagrant ssh</b>

Now, All is set.

Enjoy development with PHP.


Thanks to <a href='https://github.com/jeffreyway/'>Jeffrey Way</a>

