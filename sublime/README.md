# sublime

Erro ao instalar package manager


import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)



```sh
cd ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/
git clone git://github.com/wbond/sublime_package_control.git Package\ Control
cd Package\ Control
git checkout python3

# restart Sublime Text 3 and you should have Package Control working
```
[fonte](https://gist.github.com/moomerman/4674060)

Despois descompactei manualamnete o pacote /home/adriano/.config/sublime-text-3/Installed Packages/0_package_control_loader.sublime-package
