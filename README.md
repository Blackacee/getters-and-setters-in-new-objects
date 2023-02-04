# getters-and-setters-in-new-objects

var date = {
 year: '2017',
 month: '02',
 day: '27',
 get date() {
 // Get the date in YYYY-MM-DD format
 return `${this.year}-${this.month}-${this.day}`
 },
 set date(dateString) {
 // Set the date from a YYYY-MM-DD formatted string
 var dateRegExp = /(\d{4})-(\d{2})-(\d{2})/;
 
 // Check that the string is correctly formatted
 if (dateRegExp.test(dateString)) {
 var parsedDate = dateRegExp.exec(dateString);
 this.year = parsedDate[1];
 this.month = parsedDate[2];
 this.day = parsedDate[3];
 }
 else {
 throw new Error('Date string must be in YYYY-MM-DD format');
 }
 }
};
