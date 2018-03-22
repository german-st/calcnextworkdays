[![NPM](https://nodei.co/npm/node-red-contrib-calc-next-work-days.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/node-red-contrib-calc-next-work-days/)

![Build](https://travis-ci.org/german-st/calcnextworkdays.svg?branch=master)
[![npm](https://img.shields.io/npm/dt/node-red-contrib-calc-next-work-days.svg)](https://www.npmjs.com/package/node-red-contrib-calc-next-work-days)
# README #
Node for Node-RED.

A simple node that calculates the next (or several) working day given the holidays and working days off.

### Install ###

Install latest release: `npm i -g node-red-contrib-calc-next-work-days`

### Inputs

`msg.date` date

The start date for calculation(this day is counted as the first).

`msg.countworkdays` number

Number of working days to be calculated in result.You can specify in the configuration node or stream mode.

`msg.holidays` array

Array of dates with holidays

`msg.workweekends` array

Array of dates with working weekends days. Not required.

`msg.typeweekend` string

Weekend type. You can specify in the configuration node or stream mode. `satsun`, `frisat` or `withoutweekends` values.

### Outputs

`msg.workdays` array

Result. Array of arrays the following working days.The count will be equal to `msg.countworkdays`

The first element contains the calculated date

The second element contains the day number relative to the primary date

`0: "2018-05-10T00:00:00.000Z"`

`1: 1`

### Details

`msg.payload` Not affected or processed. The output remains the same.

`msg.holidays` Array of dates with holidays. Dates must be in javascript date format. Example `["2018-05-01 00:00:00.000Z","2018-05-02 00:00:00.000Z"]`

`msg.workweekends` Array of dates with working weekends days. Dates must be in javascript date format.

Example `["2018-05-12 00:00:00.000Z","2018-05-13 00:00:00.000Z"]` This array can be empty. Then the calculation will be made considering the holidays and usual weekends days sets in "Weekends days" section.

`msg.workdays` Calculated result. Array with calculated working days. The number of elements (days) is equal to that set in `msg.countworkdays`.