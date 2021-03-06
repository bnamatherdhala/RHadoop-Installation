##Install R with shared libraries

Install required Ubuntu applications for R and it's packages
```
  sudo apt-get update
  sudo apt-get install build-essential libcurl4-gnutls-dev ant git libssl-dev make
```

Read [instruction](http://cran.r-project.org/bin/linux/ubuntu/README) here before install R in Ubuntu. 
Get sudo access and add below entries in ```/etc/apt/sources.list``` file to obtain latest R packages. Remember to update below lines with your Ubuntu code name. 

```
  deb http://cran.ms.unimelb.edu.au/bin/linux/ubuntu saucy/
  deb http://mirror.cse.iitk.ac.in/ubuntu saucy-backports main restricted universe
```
The Ubuntu archives on CRAN are signed with the key of "Michael Rutter" with key ID E084DAB9.  To add the key to your
system with below commands. Exit from the current terminal.
```
  gpg --keyserver keyserver.ubuntu.com --recv-key E084DAB9
  gpg -a --export E084DAB9 | sudo apt-key add -
  exit
```
Install and update basic and R related required applications 
```
  sudo apt-get build-dep r-base
  sudo apt-get install r-base r-recommended r-base-dev
  sudo apt-get install r-base-html r-doc-pdf
  sudo apt-get install littler
```

Now check R installed correctly compiled using --enable-R-shlib. ```sudo R CMD config --ldflags``` It will print a path, take the printed path and check the "libR.so" file exist in that location. If you couldn't see the file then something must gone worng.

If you install R successfully, follow next steps



