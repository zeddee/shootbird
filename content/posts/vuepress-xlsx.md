---
title: "Using an XLSX file as a simple CMS with Vuepress"
date: 2019-07-20T04:40:24+08:00
showDate: true
draft: false
tags: ["blog","vuepress","xlsx","cms"]
---

# Using an XLSX file as a simple CMS with Vuepress

Excel spreadsheets are an extremely powerful and versatile data format to work with,
but comes with the baggage of Microsoft Office formats having been closed proprietary formats for
the longest time, and that they're expensive to read i.e. they're binary files that cannot be read
by opening them in a text editor.

Fortunately, other tools such as OpenOffice/LibreOffice and the Google Suite have allowed us
to work with these Office formats without having to be locked into a particular piece of software.
Plus any of the modern Office documents affixed with an "x" use the
[OpenXML](https://github.com/OfficeDev/office-content/tree/master/en-us/OpenXMLCon) format,
which Microsoft has provided an SDK for, allowing us to work with Office formats programmatically.

## Usage

I've put up a sample repository showing how this would work here: https://github.com/zeddee/vuepress-and-xlsx

The repository uses:

- [Vuepress](https://vuepress.vuejs.org/guide/)
- [js-xlsx](https://github.com/SheetJS/js-xlsx)

To run this sample repository:

1. Clone with `git clone git@github.com:zeddee/vuepress-and-xlsx.git`
2. Install with `yarn install`
3. Run with `yarn dev` and access the site on `localhost:8080`

Modify `site/README.md` and `sample.xlsx` to poke around and see how it works.

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

