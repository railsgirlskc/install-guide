# Linux

## _1._ Install Rails

To install the Ruby on Rails development environment you just need to copy the line below for your Linux distribution \(Ubuntu or Fedora\), paste it in the Terminal and press Enter. Enjoy the text flying on the screen; it will take quite some time. Grabbing a refreshing drink before starting is encouraged.

**For Ubuntu:**

```text
sudo apt-get install curl
bash < <(curl -sL https://raw.github.com/railsgirls/installation-scripts/master/rails-install-ubuntu.sh)
```

If you are going to use RVM installations with gnome-terminal, you’ll probably need to change it’s default options before you can see and use the right Ruby and Rails versions. Find out how: [RVM documentation](http://rvm.io/integration/gnome-terminal).

**For Fedora:**

```text
bash < <(curl -sL https://raw.github.com/railsgirls/installation-scripts/master/rails-install-fedora.sh)
```

Make sure that all works well by running the application generator command.

```text
rails new myapp
```

## _2._ Install a text editor to edit code files

For the workshop we recommend the text editor Sublime Text.

* [Download Sublime Text and install it](http://www.sublimetext.com/2). Just to make sure that you’re not mixing up using your terminal or text-editor: change the theme of your Sublime text-editor, choosing one of the following: “iPlastic”, “Slush & Poppies”, or “Zenburnesque”.

## _3._ Update your browser

Open [whatbrowser.org](http://whatbrowser.org/) and update your browser if you don’t have the latest version.

## _4._ Check the environment

Check that everything is working by running the application generator command.

```text
rails new myapp
cd myapp
rails server
```

Go to `http://localhost:3000` in your browser, and you should see the ‘Yay! You’re on Rails!’ page.

Now you should have a working Ruby on Rails programming setup. Congrats!

**Coach:** We recommend to verify by using the scaffold command and inputting data with the generated page with coaches to ensure everything is working. Also: remove the test app `myapp` to make super sure no-one is working in the wrong folder, following the steps of the workshop.

