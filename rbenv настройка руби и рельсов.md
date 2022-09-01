Установка rbenv и rbenv-build из репозитория github

cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
применить настройки для текущей оболочки
source ~/.bashrc

Проверить доступные для устаноки версии
rbenv install -l

Установка руби версии…

rbenv install 2.7.1

Установить версию как глобальную(главную, дефолтную)
 
rbenv global 2.7.1
проверка 
ruby -v

Установить бандлер
gem install bundler

#!/bin/bash
/usr/bin/sudo rm -rf $HOME/.rvm $HOME/.rvmrc /etc/rvmrc /etc/profile.d/rvm.sh /usr/local/rvm /usr/local/bin/rvm
/usr/bin/sudo /usr/sbin/groupdel rvm
/bin/echo "RVM is removed. Please check all .bashrc|.bash_profile|.profile|.zshrc for RVM source lines and delete
or comment out if this was a Per-User installation."

