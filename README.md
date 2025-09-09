# university-web-dev-1

# Scenario
A list of medication, displaying their name, whether there is a contraindication and any medication it interacts with. Allowing users to add, remove and edit medications.
# Basic requirement implementation

## Database
A singular database is used and is in first normal form.
The database has been established through creating a new table migration 
and seeding the database through "MedicationSeeder". This created a table accessible
from phpMyAdmin with 10 different elements within 3 distinguished columns;
Name, Contraindication and medication interaction.

## Medication Controller
Contains the functions: index, create, about, store, show, edit, update and destroy.

### Medication Controller: Index function
Takes in all the data from the database and sets it equal to the medications variable that is used to display the information in the view.
Returns the index view.

### Medication Controller: Create function
Returns the create view.

### Medication Controller: About function
Returns the about view.

### Medication Controller: Store function
Creates a new Medication object, uses the applied column names (name, contraindication and medication_interaction) and applies the added information into the save function.
Returns the show view.

### Medication Controller: Show function
Takes in an id value, finds the medication that corresponds to the provided id and returns the show view.

### Medication Controller: Edit function
Uses the id to edit changes to either of the 3 fields (name, contraindication and medication_interaction)
Returns the edit view.

### Medication Controller: Update function
Allows for the changes made through the edit function to be saved.
Returns the index view.

### Medication Controller: Destroy function
Removes medication through the use of it's id
Returns the index view.

## CSS Style
Uses a contrast of blue and black for the main theme with mainly white text.
Contains a navigation bar with colour changing buttons when hovered over.

## Views
Contains the Layout, about, create, edit, index and show blades.

### Layout view
Contains a layout which the other blades follow.

### About View
Contains brief information to display.

### Create View
Contains fields to enter desired medication names, contraindications and interactions to add to the list.

### Edit View
Contains the same as the create view with an additional hidden Id field.

### Index View
Home page listing medications.

### Show View
Displays the information from the database once a medication has been selected from the home page.

## Routes
Routes for index, create, about, store, show, edit, update and destroy.

# Additional requirements implemented

## Pagination
Implemented within the index function to allow for 4 items per page with Next and preview functions, and page numbering.
Initially with the pagination applied large arrows were displayed, I edited the tailwind vendor view to remove these.

## Input validation
Implemented within the store and update function, restricting what can be stored. Name is a required field that is a string with a minimum character length of 5 and a maximum of 20. Contraindication field is a required field that is a string with a minimum character length of 2 and a maximum character length of 3. Medication interaction isn't a required field but if it is added it is a string with a minimum of 5 and a maximum of 20 characters.

## Search Facility
Implemented within the index function, allowing for a search bar on the index page. Although this function does allow for a search page to be requested, the view page for the search was unsuccessfully implemented.
