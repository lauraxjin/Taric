# TARIC-code
==========
The TARIC-code web service assists users ( primarily EU custom officials and international exporters who export goods to the EU)to identify a particular good's TARIC-code(HS international trade product code plus an additional 4 digit EU code) from the HS hierarchical rules.

Data is divided in the hierarchical structure specified in the HS handbook(21 Sections and 96 Chapters).

  - **list-rule-names.html** shows a list of all the rules in the handbook. This page supports Get and Head. This is page also contains a search box that returns rules that contain the users' query words/phrases.
  - **one-rule.html** shows rule name, the Taric code related to each rule, and the rule's description. This page alos allows the user to update rule name, chapter name, and rule description. This page supports Post and Head.
  - **list-chapters.html** Lists the names of all chapters entered in the database. The add/update form allows the users to edit Taric code, chapter name, and chapter description information. This page supports Post and Head.
  - **one-chapter.html** shows chapter name, chapter description, and all the rules (with chapter name added to the beginning of each rule name). This page also allows users to add a new rule with rule name and rule desciption. This page supports Post and Head.

## Attribute values: Id, Class, Name, and Rel

### Id attribute values: 
  
  **publisher** : Applied to all footer tag. The footer has information about orginal publisher of the rules(European Union Trade Commission Official Taric Site), creater(me), editor(me). And it is present in all four ejs files.
  
### Class attribute values:
  
  **control** : Applied to div tags that contains a form that can either update or create rules/chapters. It is also present in all four ejs files.
 
### Name attribute values:
 
  **_method** : Applied to the INPUT tag. Posts new chapter in list-chapter.ejs's form area. Update rules(rule name, chapter and description) in one-rule.ejs form.
  
  **item[id]** : Applied to the INPUT tag. new chapter to be added is given an id and gets to be stored in an array in couchDB.

  **item[name]** : Like above, new chapter name added gets to be stored in an array in couchDB.
 
  **item[description]** : Like above, new chapter description added gets to be stored in an array in couchDB.
  
  **name** : In list-rule-name.ejs. It is used for the search function. The 'name' inputed to the search form is compared with the rules we have and returns the rule that matches.
   
  **item[rule-name],item[chapter], item[rule]** : In one-rule.ejs. Updated rule informaiton(rule name, chapter, rule description) replaces the existing rule information on this page.
    
### Rel attribute values:
  
  **stylesheet** : For linking stylesheet in the head tag. Present in all four ejs pages.

## Types

  **chapter** : represent individual chapter to be stored.
  
  **rule-name** : represent individual rule-name to be stored.

## Properties(id)

  **/chapters/** : represent list of chapters. If the update/create has no errors, new chapter related information gets stored in a list and given ids.
  
  **/rule-names/** : represent list of rule-names. If the update/create has no errors, new rule related information gets stored in a list and given ids.
  
    
