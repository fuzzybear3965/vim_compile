# Introduction


It's a pain trying to find a good copy of Vim that has all of the features I
need (Lua and Python support) and that's compiled regularly. So, I'm putting a
repository on Github that should make it easier for other people to compile Vim
for themselves on Windows. I list the dependencies below.

I automate the execution of ``vim_build.bat`` by creating a Windows Task. I synchronize the latest build with all of the Windows machines that I own using Syncthing.

# Dependencies

vim_build.bat uses git to grab the latest version of Vim. mingw32-make is used
to perform the compilation. This batch script has been tested on
mingw-w64 (i686-5.3.0-posix-dwarf-rt_v4-rev0).
* Vim
* Git
* Mingw-w64
* Add the above programs to your path

### Notes 

  * If you use credentials with your Github RSA key then I strongly recommend using the secure hypertext transfer protocol (``https://github.com``) to clone the Vim repository instead of using the secure shell protocol (``git@github.com``).
  * Make sure to select i686 and POSIX when configuring the installation of mingw-w64.
  * You can edit the environment variables in the batch file to point to the proper paths.
  * You can edit the environment variables in the ``Make_ming.mak`` file to point to the proper paths.

# Room for Improvement
* Right now there is no mechanism to check/handle errors nicely when compiling from the batch file. I would like a way to do this. Unsuccessful compilations can corrupt the repositories and require a clean. "Cleaning" entails deleting the repository from my hard drive and cloning Vim, again.
* I have not managed to compile a 64-bit version of Vim for Windows, yet. This is a big goal.
* This version of the batch file does not accept command line arguments. This would be something that I would like to implement in the future.
* Right now, only Python27 and Lua support has been successfully obtained with this batch file. Python33, Perl and Ruby are the next languages for which I would like to add support.
* I need to add a license. But, feel free to use these files however you wish in the meantime. I don't need accreditation.
