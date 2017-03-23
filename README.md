Exercises [Chapter 2.2.1]

1. (For readers who know CSS) Create a new user, then use your browser’s HTML inspector to determine the CSS id for the text “User was successfully created.” What happens when you refresh your browser?

The id of the div is "notice". When I refresh the page, the div remains there and visible, but with no text.

2. What happens if you try to create a user with a name but no email address?

It works.

3. What happens if you try create a user with an invalid email address, like “@example.com”?

It works too.

4. Destroy each of the users created in the previous exercises. Does Rails display a message by default when a user is destroyed?

Yes, it shows "User was successfully destroyed".

=========================================================

Exercises [Chapter 2.2.2]

1. By referring to Figure 2.11, write out the analogous steps for visiting the URL /users/1/edit.

The browser issues a request for the /users/1/edit URL.
Rails routes /users to the edit action in the Users controller.
The index action asks the User model to retrieve the user that contains the id "1" (User.all).
The User model pulls the corresponding user from the database.
The User model returns the specific user to the controller.
The controller captures the user in the @user variable, which is passed to the edit view.
The view uses embedded Ruby to render the form as HTML with the user content.
The controller passes the HTML back to the browser.

2. Find the line in the scaffolding code that retrieves the user from the database in the previous exercise.

SQL (0.2ms)  DELETE FROM "users" WHERE "users"."id" = ?  [["id", 5]]

3. What is the name of the view file for the user edit page?

edit.html.erb

=========================================================

Exercises [Chapter 2.3.1]

1. (For readers who know CSS) Create a new micropost, then use your browser’s HTML inspector to determine the CSS id for the text “Micropost was successfully created.” What happens when you refresh your browser?

The id of the div is "notice". When I refresh the page, the div remains there and visible, but with no text.

2. Try to create a micropost with empty content and no user id.

It works too, as it remains with no information at all.

3. Try to create a micropost with over 140 characters of content (say, the first paragraph from the Wikipedia article on Ruby).

That works too, as the validation is not present.

4. Destroy the microposts from the previous exercises.

Done! :)

=========================================================

Exercises [Chapter 2.3.2]

1. Try to create a micropost with the same long content used in a previous exercise (Section 2.3.1.1). How has the behavior changed?

It denies the input and shos an error (Content is too long (maximum is 140 characters)

2. (For readers who know CSS) Use your browser’s HTML inspector to determine the CSS id of the error message produced by the previous exercise.

The id is "error_explanation".

=========================================================

Exercises [Chapter 2.3.4]

1. By examining the contents of the Application controller file, find the line that causes ApplicationController to inherit from ActionController::Base.

class ApplicationController < ActionController::Base (The less than symbol)

2. Is there an analogous file containing a line where ApplicationRecord inherits from ActiveRecord::Base? Hint: It would probably be a file called something like application_record.rb in the app/models directory.

class ApplicationRecord < ActiveRecord::Base
