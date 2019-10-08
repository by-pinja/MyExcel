# MyExcel

## npm

* Install

```
npm i --save myexcel
```

* Code

```
const myexcel = require('myexcel');

const testData = [
  { 'Column 1': 'Test' },
  { 'Column 1': 'Test Again' },
];

const excel = myexcel.new('Calibri light 10 #333333');

const headers = Object.keys(testData[0]);

const formatHeader = excel.addStyle({ border: 'none,none,none,thin #333333',
  font: 'Calibri 12 #0000AA B' });

for (let i = 0; i < headers.length; i++) {
  excel.set(0, i, 0, headers[i], formatHeader);
  excel.set(0, i, undefined, 'auto');
}

for (let i = 0; i < testData.length; i++) {
  const data = Object.values(testData[i]);
  for (let j = 0; j < headers.length; j++) {
    excel.set(0, j, i + 1, data[j].toString());
  }
}

excel.generate('test.xlsx', () => {
  console.log('exporting is done');
});
```

## Browser
Simple generator of XLSX files from Javascript

To demo it try [this sample](http://jsegarra1971.github.io/MyExcel/sample.html). Look at its source code.

It so simple that no documentation is required. Contact me for bugs, requests, ideas,...

Licensed under MIT, but if you use it, I´d appreciate if you let me know.

