# angular-code-snippets
Some useful code snippets for Angular.io

#### GPS coordinates validator function ####
```javascript
private coordinatesValidator(option: string) {
    return (control: FormControl): { [key: string]: any } | null => {
      const value: string = control.value;
      const regex =
        option === 'lat'
          ? /^(\+|-)?(?:90(?:(?:\.0{1,6})?)|(?:[0-9]|[1-8][0-9])(?:(?:\.[0-9]{1,6})?))$/
          : /^(\+|-)?(?:180(?:(?:\.0{1,6})?)|(?:[0-9]|[1-9][0-9]|1[0-7][0-9])(?:(?:\.[0-9]{1,6})?))$/;
      const parsedValue = !regex.test(value);
      return parsedValue
        ? { invalidCoordinates: { coordinates: value } }
        : null;
    };
  }
  ```

# Docker cheatsheet

### Launch container from docker-compose file

```docker-compose up --build -d --force-recreate```

### List images and containers

```docker ps -a``` or ```docker container ls -a```

Show list of all containers (-a). You can skip -a option to show only running.

```docker images -a```

Show list of all (-a) images

### Remove imageas and containers

_Remove all unused images:_

```docker image prune -a -f```

Removes all (-a) unused images without confirmation (-f)

_Remove all stopped containers:_

```docker container prune -f```

### Run terminal on detached active container

_Launch interactive terminal:_

```docker exec -it 466a13554655 /bin/sh```

_Exit interactive terminal:_

```exit```
