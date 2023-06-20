# Lecture05

1. EC2・RDS・VPC・S3・ALBの設定

必要なAWSリソースを設定。(EC2/RDS/VPC/S3/ALB)

![EC2status](./Lecture05_Pic/EC2.PNG)

![RDSstatus](./Lecture05_Pic/RDS.PNG)

![VPCstatus](./Lecture05_Pic/VPC.PNG)

![VPCstatus](./Lecture05_Pic/S3_bucket.PNG)

![ALBstatus](./Lecture05_Pic/ALB.PNG)

Windows環境からTeratermにてSSH接続(ED25519を使用)
![ALBstatus](./Lecture05_Pic/Teraterm.PNG)

2. EC2環境にアプリ動作環境を構築
   ```
   #アップデート+諸々インストール
sudo yum update
sudo yum -y install git make gcc-c++ patch openssl-devel libyaml-devel libffi-devel libicu-devel libxml2 libxslt libxml2-devel libxslt-devel zlib-devel readline-devel


#Node.js Yarn
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
. ~/.nvm/nvm.sh
nvm install v16.20.0

curl -sL https://dl.yarnpkg.com/rpm/yarn.repo | sudo tee /etc/yum.repos.d/yarn.repo
sudo yum -y install yarn

#rbenv
git clone https://github.com/sstephenson/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
source ~/.bash_profile

#ruby-build
git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build
rbenv rehash

#Ruby 3.1.2
export -p TMPDIR="$HOME/"s

rbenv install -v 3.1.2
rbenv global 3.1.2
rbenv rehash
ruby -v

#MySQL8.0
curl -fsSL https://raw.githubusercontent.com/MasatoshiMizumoto/raisetech_documents/main/aws/scripts/mysql_amazon_linux_2.sh | sh

#bundle2.3.14
gem install bundler -v 2.3.14

#nginxインストール
sudo amazon-linux-extras install -y  nginx1

sudo yum -y  installl ImageMagick
   ```
