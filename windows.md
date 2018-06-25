# Windows

## _1._ Install Rails

Download [RailsInstaller](https://s3.amazonaws.com/railsinstaller/Windows/railsinstaller-3.3.0.exe) and run it. Click through the installer using the default options.

### **1a. Enable copy and paste in Windows Command Prompt**

For Windows 10 users:

Open `Command Prompt with Ruby and Rails`. Right-click on the command prompt’s title bar, and choose “Properties”. Navigate to the “experimental” tab, and check the “Enable new Ctrl key shortcuts” option \(you may need to check the “Enable experimental console features” option first\).

For other Windows versions:

To paste a text in the command prompt window you’ll need to use the mouse \(right-click on the window –&gt; paste\).

### **1b. Install Rails**

In the `Command Prompt with Ruby and Rails`, run the following command:

```text
rails -v
```

If you see the following message:

```text
the system cannot find the path specified
```

This can happen when the installer cannot correctly setup the paths required to run rails. It’s nothing serious, we can fix this in different ways but the easiest is by manually installing the rails gem with the following command:

```text
gem install rails bundler --no-document
```

This will \(re\)install rails correctly and running:

```text
rails -v
```

Should print the currently installed rails version number \(your version may differ\):

```text
Rails 5.1.1
```

If the Rails version is less than 5.1, update it using a following command:

```text
gem update rails --no-document
```

## Possible errors

### Gem::RemoteFetcher error

If you get this error when running `rails new railsgirls` or `gem update rails`:

```text
Gem::RemoteFetcher::FetchError: SSL_connect returned=1 errno=0 state=SSLv3 read
server certificate B: certificate verify failed (https://rubygems.org/gems/i18n-0.6.11.gem)
```

This means you have an older version of Rubygems and will need to update it manually first verify your Rubygems version

```text
gem -v
```

If it is lower than `2.6.5` you will need to manually update it:

First download the [ruby-gems-update gem](https://rubygems.org/gems/rubygems-update-2.6.11.gem). Move the file to `c:\\rubygems-update-2.6.11.gem` then run:

```text
gem install --local c:\\rubygems-update-2.6.11.gem
update_rubygems --no-document
gem uninstall rubygems-update -x
```

Check your version of rubygems

```text
gem -v
```

Make sure it is equal or higher than `2.6.11`. Re-run the command that was failing previously.

If you are still running into problems you can always find the latest version of rubygems online at [rubygems.org](https://rubygems.org/pages/download). If you click on **GEM** you will get the latest version.

### During bundle install

The `Gem::RemoteFetcher::FetchError: SSL_connect` can also occur during the `bundle install` stage when creating a new rails app.

The error will make mention of [bit.ly/ruby-ssl](http://bit.ly/ruby-ssl). What is relevant for Windows users at this point is [this GitHub gist](https://gist.github.com/867550). The described manual way has proven to be successful to solve the `bundle install` error.

#### ‘x64\_mingw’ is not a valid platform\` Error {#x64_mingw-is-not-a-valid-platform-error}

Sometimes you get the following error when running `rails server`: `'x64_mingw' is not a valid platform` If you experience this error after using the RailsInstaller you have to do a small edit to the file `Gemfile`:

Look at the bottom of the file. You will probably see something like this as one of the last lines in the file:`gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw]`. If you have this line with `:x64_mingw`, then please delete the `:x64_mingw`part. In the end it should just say: `'tzinfo-data', platforms: [:mingw, :mswin]`

After you did that, please use your Command Prompt again and type `bundle update`.

## _2._ Install a text editor to edit code files

For the workshop we recommend the text editor Atom.

* [Download Atom and install it](https://github.com/atom/atom/releases/latest)
  * Download an atom zip file for windows and decompress it.
  * Copy the folder into your Program Files.
  * Launch atom in the folder.

If you are using Windows Vista or older versions, you can use another editor [Sublime Text 2](http://www.sublimetext.com/2). Just to make sure that you’re not mixing up using your command prompt or text-editor: change the theme of your Sublime text-editor, choosing one of the following: “iPlastic”, “Slush & Poppies”, or “Zenburnesque”.

## _3._ Update your browser

If you use Internet Explorer, we recommend installing [Firefox](http://guides.railsgirls.com/mozilla.org/firefox) or [Google Chrome](http://guides.railsgirls.com/google.com/chrome).

Open [whatbrowser.org](http://whatbrowser.org/) and update your browser if you don’t have the latest version.

## _4._ Install Node.js

* Go to [https://nodejs.org/](https://nodejs.org/) and install Node.js LTS package
* Reopen your Rails Command Shell

Check your version of node

```text
node --version
```

Make sure it is displaying version number.

## _5._ Check the environment

Check that everything is working by running the application generator command.

```text
rails new myapp
cd myapp
rails server
```

Go to `http://localhost:3000` in your browser, and you should see the ‘Yay! You’re on Rails!’ page.

Now you should have a working Ruby on Rails programming setup. Congrats!

**Coach:** We recommend to verify by using the scaffold command and inputting data with the generated page with coaches to ensure everything is working. Also: remove the test app `myapp` to make super sure no-one is working in the wrong folder, following the steps of the workshop.

