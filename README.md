

    # ssh into ravello oob-mgmt-server as cumulus with password CumulusLinux!
    # sftp the VX onie installer image as onie-installer into /home/cumulus

    sudo apt-get update
    sudo apt-get install -qy git apache2 isc-dhcp-server
    git clone https://github.com/cumulusnetworks/ravello-demo-bootstrap
    cd ravello-demo-bootstrap
    sudo cp ./etc/dhcp/* /etc/dhcp
    sudo cp ./var/www/html/* /var/www/html
    sudo cp ~/onie-installer /var/www/html
    sudo service isc-dhcp-server restart
