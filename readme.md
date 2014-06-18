# fng-select2

Plugin for forms-angular that adds select2 support.

## Usage

    bower install fng-select2
    
Add the following lines to your index.html (or equivalent) file

    <link rel="stylesheet" href="/bower_components/select2/select2.css">
    <script src="/bower_components/jquery/jquery.js"></script>
    <script src="/bower_components/angular-ui-select2/src/select2.js"></script>
    <script src="/bower_components/select2/select2.js"></script>
    
In your Mongoose schemas you can set up fields like this:
       
    colour: {type: String, enum: ['Red', 'Orange', 'Yellow', 'Green', 'Blue', 'Indigo', 'Violet'], form:{select2:true}}
    lookup: { type: Schema.Types.ObjectId, ref: 'anotherModel', form: {select2: {}}},
    
In this case forms-angular will look up all the values in the anotherModel collection when the form is loaded.  In the
case where the collection is large you should use the fngAjax option 

    lookup2: { type: Schema.Types.ObjectId, ref: 'largeModel', form: {select2: {fngAjax:true}}} 
    
which instructs the program to use ajax calls to query the server rather than downloading the table.

