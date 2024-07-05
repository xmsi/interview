# Cheatsheet to defeat bugs

### *php.validate.executablepath in VSCODE; for sail docker laravel*

``sudo touch /usr/local/bin/php``\
``sudo chmod +x /usr/local/bin/php``

inside /usr/local/bin/php should be:

```
path=$(printf '%s\n' "${PWD##*/}")
command="docker exec ${path}-laravel.test-1 php "$@""
echo "Running php on docker ${path}-laravel.test-1"
$command
```

Check with ``php -v`` inside your folder
