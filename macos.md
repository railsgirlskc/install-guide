# MacOS

## _1._ Let’s check the version of the operating system.

Click the Apple menu and choose _About this Mac_.

![Apple menu](http://guides.railsgirls.com/images/1.png)

## _2._ In the window you will find the version of your operating system.

If your version number starts with 10.6, 10.7, 10.8, 10.9, 10.10, 10.11 10.12, 10.13, or 10.14 this guide is for you. If it’s something else, we can setup your machine at the event.

![About this Mac dialog](http://guides.railsgirls.com/images/2.png)

### _3a._ If your OS X version is 10.9 or higher:

 We are installing homebrew and rbenv.

#### **3a1. Install Command line tools on terminal:**

```text
xcode-select --install
```

#### **3a2. Install Homebrew:**

```text
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

#### **3a3. Install rbenv:**

```text
brew update
brew install rbenv
brew upgrade ruby-build
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
source ~/.bash_profile
```

#### **3a4. Build Ruby with rbenv:**

You can find the newest version of Ruby with the command “rbenv install -l”.

```text
rbenv install 2.6.5
```

If you got "BUILD FAILED \(OS X 10.14.6 using ruby-build 20191004\)"

```text
brew install openssl
RUBY_CONFIGURE_OPTS=--with-openssl-dir=/usr/local/Cellar/openssl/1.0.2t rbenv install 2.6.5
```

If you got “OpenSSL::SSL::SSLError: … : certificate verify failed” error, try it this way.

```text
brew install curl-ca-bundle
cp /usr/local/opt/curl-ca-bundle/share/ca-bundle.crt `ruby -ropenssl -e 'puts OpenSSL::X509::DEFAULT_CERT_FILE'`
```

#### **3a5. Set default Ruby:**

```text
rbenv global 2.6.5
```

#### **3a6. Install rails:**

```text
gem install rails --no-document
```

### _3b._ If your OS X version is 10.6, 10.7, or 10.8:

Download the RailsInstaller for your version of OS X:

* [RailsInstaller for 10.7 and 10.8](http://railsinstaller.s3.amazonaws.com/RailsInstaller-1.0.4-osx-10.7.app.tgz) \(325MB\)
* [RailsInstaller for 10.6](http://railsinstaller.s3.amazonaws.com/RailsInstaller-1.0.4-osx-10.6.app.tgz) \(224MB\)

Double click the downloaded file and it will unpack it into the current directory. Double click the the newly unpacked ‘RailsInstaller-1.0.4-osx-10.7.app’ or ‘RailsInstaller-1.0.4-osx-10.6.app’ and follow the instructions. It will open a README file with ‘Rails Installer OS X’ at the top. Please **ignore** the instructions in this file.

If the Rails version wasn’t the latest, you could update it using a following command on terminal.

```text
gem update rails --no-document
```

## _4._ Install a text editor to edit code files

For the workshop we recommend the text editor Atom.

* [Download Atom and install it](https://atom.io/)

If you are using Mac OS X 10.8 or older versions, you can use another editor [Sublime Text 2](http://www.sublimetext.com/2). 

## _5._ Update your browser

Open [whatsmybrowser.org](https://www.whatsmybrowser.org/) and update your browser if you don’t have the latest version.

## _6._ Check the environment

Check that everything is working by running the application generator command.

```text
rails new testapp
cd testapp
rails server
```

Go to `http://localhost:3000` in your browser, and you should see the ‘Yay! You’re on Rails!’ page.

Now you should have a working Ruby on Rails programming setup. Congrats!

**Coach:** We recommend to verify by using the scaffold command and inputting data with the generated page with coaches to ensure everything is working. Also: remove the test app `testapp` to make super sure no-one is working in the wrong folder, following the steps of the workshop.

## 7. Go through the Workshop Guides

[https://railsgirlskc.gitbook.io/workshop-guide/](https://railsgirlskc.gitbook.io/workshop-guide/)

