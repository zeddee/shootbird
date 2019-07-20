---
title: "Using an XLSX file as a simple CMS with Vuepress"
date: 2019-07-20T04:40:24+08:00
showDate: true
draft: false
tags: ["blog","vuepress","xlsx","cms"]
---

Excel spreadsheets are an extremely powerful and versatile data format to work with,
but comes with the baggage of Microsoft Office formats having been closed proprietary formats for
the longest time, and that they're expensive to read i.e. they're binary files that cannot be read
by opening them in a text editor.

Fortunately, other tools such as OpenOffice/LibreOffice and the Google Suite have allowed us
to work with these Office formats without having to be locked into a particular piece of software.
Plus any of the modern Office documents affixed with an "x" use the
[OpenXML](https://github.com/OfficeDev/office-content/tree/master/en-us/OpenXMLCon) format,
which Microsoft has provided an SDK for, allowing us to work with Office formats programmatically.

## Using the Sample Repository

I've put up a sample repository showing how this would work here: https://github.com/zeddee/vuepress-and-xlsx

The repository uses:

- [Vuepress](https://vuepress.vuejs.org/guide/)
- [js-xlsx](https://github.com/SheetJS/js-xlsx)

To run this sample repository:

1. Clone with `git clone git@github.com:zeddee/vuepress-and-xlsx.git`
2. Install with `yarn install`
3. Run with `yarn dev` and access the site on `localhost:8080`

Modify `site/README.md` and `sample.xlsx` to poke around and see how it works.

## Writing it Yourself

First, we'll need to get a basic instance of Vuepress up and running.
Make sure that you have [NodeJS 10.16](https://nodejs.org/en/) or newer installed,
and (optionally) [Yarn](https://yarnpkg.com/en/).

Install `vuepress` and `js-xlsx` by running in the terminal:

```
npm i vuepress xlsx
```

Then create an XLSX file named `workbook_one.xlsx` with a spreadsheet tool of your choice, and create a table that looks like this:

<table>
<thead>
<th>Column 1</th>
<th>Column 2</th>
<th>Column 3</th>
</thead>
<tbody>
<tr><td>Item 1</td><td>Item 2</td><td>Item 3</td></tr>
<tr><td>Item 4</td><td>Item 5</td><td>Item 6</td></tr>
<tr><td>Item 7</td><td>Item 8</td><td>Item 9</td></tr>
</tbody>
</table>

Then, in your project directory, we'll create an empty `README.md` file
(**IMPORTANT**: The "readme" file _must_ be named `README.md`, not `README.MD`, or Vuepress will not pick it up!)
that will act as a placeholder for now.

Next we'll create a Javascript file named `crunch_spreadsheet.js`, and add the following code to it:

```javascript
const fs = require('fs')
const XLSX = require('xlsx')

const workbook = XLSX.readFile('workbook_one.xlsx')

// export all sheets to json

let runExport = (workbook) => {
    for (let i = 0; i < workbook.Workbook.Sheets.length; i++){
        let ws = workbook.Sheets[workbook.SheetNames[i]]
        let jsonOutput = XLSX.utils.sheet_to_json(ws)
        fs.writeFile(`${workbook.SheetNames[i]}.json`, JSON.stringify(jsonOutput), (err)=>{
            if (err) return console.error(err)

            console.log(`${workbook.SheetNames[i]} was saved!`)
        })
    }
}

runExport(workbook)
```

In the code snippet above, we:

1. Use the `xlsx` library and call `.readFile()` on our spreadsheet `workbook_one.xlsx` to begin processing it.
2. Loop over the `workbook` object that we get back from `.readFile()`, making sure that we get all the worksheets in the workbook/spreadsheet file.
3. For each worksheet we find, we call `XLSX.utils.sheet_to_json(worksheet)` to extract the spreadsheet and convert it to JSON.
4. Write that extracted JSON to a `.json` file.

To see our new Javascript file in action, run in the terminal:

```bash
node crunch_spreadsheet.js
```

You should see a new `Sheet 1.json` file (the default name of the first spreadsheet in a workbook in Google Sheets and Excel).

Now, edit `README.md` and add the following code:

```html
<table>
<thead>
<th>Column 1</th>
<th>Column 2</th>
<th>Column 3</th>
<thead>
<tbody>
<tr v-for="i in sheet1">
<td>{{ i["Column 1"] }}</td>
<td>{{ i["Column 2"] }}</td>
<td>{{ i["Column 3"] }}</td>
</tr>
<tbody>
</table>

<script>
import sheet1 from 'Sheet 1.json'

export default {
    data() {
        return {
            sheet1: sheet1
        }
    }
}
</script>
```

Here, we've:

1. Created a `<script>` within our markdown file that
    a. Imports data from our json spreadsheet and assigns it to the `sheet1` variable.
    b. Exposes `sheet1` to the Vue framework.
2. Created a HTML `<table>` with the headings that we expect from the spreadsheet we're feeding into it.
3. Write a loop using the `v-for` directive that:
    a. For each row in the spreadsheet, creates
    b. 3 table cells in the spreadsheet, each grabbing an item with a specified key name from the row.

Once done, save the file and run your Vuepress site with the following command:

```bash
npx vuepress dev
```

## Why an XLSX file

The `.xlsx` file is essentially a datastore that allows us to read and write data to one or more tables.
This essentially means that it can be rigged to behave like, say, a MySQL database that backs a Wordpress instance.
(That is not to say that you _should_.)

This is particularly useful if you've got a bunch of data that's more readily dealt with as a spreadsheet
rather than a discrete set of articles. For instance, you know, tables, or when designing a D&D campaign.

But while working with spreadsheets might fit the designer's needs, one might want to present the data more
palatably than directly embedding a Google Sheet into your webpage.

## Decoupling Data from Presentation

By working with `.xslx` files programmatically, how you decide to work with and store data in a spreadsheet
and how you decide to present your data (in this case, on a website) are decoupled.

This means that you deal with data and presentation separately.
This frees you up to focus on structuring and working with your data as data,
while leaving your presentation systems (i.e. Vuepress) to deal with how your data
will be crunched and presented on a separate system.

When the presentation layer fails, you know you just need to debug the code in your presentation layer,
and not have to worry about the integrity of your data layer.

If your presentation layer fails to import data from the `.xlsx` file, you know that your data layer has failed,
so you go and fix that.

And when you update your spreadsheet, data should automatically propagate in the presentation layer, fuss free.

Working this way significantly reduces the amount of cognitive load imposed on you, the writer/data wrangler.

## Limitations

I've not tested this approach with more complex tables e.g. with multi-layered column headers, or merged cells.
As with working with data formats in general, I would suggest keeping your inputs as simple as possible,
because it keeps your mental model of the project clear and focused, and makes it easier to grok and, more importantly,
explain to yourself and anyone who wanders into your orbit.

