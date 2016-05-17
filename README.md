# FTAI

某有志メンバによるプロジェクト.備忘録も兼ねる.

## 必須環境
Ubuntu14.04推奨(Mac OS Xもギリギリセーフ).
AWSの利用も可.
ただし,導入に際しての備忘録は別途記載して環境を再現できるようにしたい.

言語は当面Pythonを用いる.環境は3.X系を使用.
Pyenv + Anaconda推奨とする.

DL frameworkには当面chainerを使用.
TensorFlow及びkerasの使用も視野に入れる.

## 環境構築

Ubuntuの導入にはVagrant + VirtualBoxを用いる.

誰かDocker整備してください.

Pythonの導入にはPyenv + Anaconda3をベースとする.

### Ubuntu14.04

OS XまたはWindowsの場合,[VirtualBox](https://www.virtualbox.org/wiki/Downloads)及び[Vagrant](https://www.vagrantup.com/downloads.html)を導入.

Vagrantのイメージは[ここ](http://www.vagrantbox.es/)にある.
> Official Ubuntu 14.04 daily Cloud Image amd64 (Development release, No Guest Additions)

terminalにて以下を実施.trustyという名称は任意.
~~~
$ vagrant box add trusty　https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box
~~~

適当なディレクトリ作ってそこに設定を置く.
~~~
$ mkdir -p ~/vagrant/projects/trusty/
$ cd ~/vagrant/projects/trusty/
$ vagrant init trusty
~~~

起動.
~~~
$ cd ~/vagrant/projects/trusty/
$ vagrant up
~~~

SSHログイン.
~~~
$ cd ~/vagrant/projects/trusty/
$ vagrant ssh
~~~

インスタンス停止.
~~~
$ cd ~/vagrant/projects/trusty/
$ vagrant halt
~~~

なお,ログインはID,Passともにvagrantになるそう.

ログインしたらUbuntuデスクトップを入れる.

~~~
apt-get install xfce4
add-apt-repository ppa:gnome3-team/gnome3
apt-get update
apt-get install gnome-shell
apt-get install ubuntu-desktop
apt-get install gdm
dpkg-reconfigure gdm
~~~
を打ち込めばOK,ubuntu-desktopだけでもいけるのかもしれない.

なお、Vagrant設定ファイルにある下記をコメントアウトすれば,VirtualBoxからGUIで起動できる.
~~~
  config.vm.provider "virtualbox" do |vb|
    # Display the VirtualBox GUI when booting the machine
    vb.gui = true

    # Customize the amount of memory on the VM:
    vb.memory = "1024"
  end
~~~

### Python




### DL framework

以下で入るはず.

GPUを使用する場合はちょっと違うので別途記載.
~~~
pip install chainer
~~~
