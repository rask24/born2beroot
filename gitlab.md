## install
- `sudo apt install -y curl openssh-server ca-certificates tzdata perl`
- `sudo apt install -y postfix`
- `curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | sudo bash`
- `sudo apt install gitlab-ee`

## configure
- `sudo vim /etc/gitlab/gitlab.rb`
- `external_url 'http://gitlab-server'`
