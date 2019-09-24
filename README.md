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
