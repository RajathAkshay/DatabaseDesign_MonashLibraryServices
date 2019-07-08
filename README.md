# DatabaseDesign_MonashLibraryServices
The local Monash Municipality maintains several libraries for its residents across the municipality.
For each branch Monash Library Services assigns a branch code (an incremental number for each branch with the first branch using a code of 100). The branch name, address and contact phone number are also recorded. Each branch is assigned a manager. Due to the small size of some of the branches a particular manager may manage several branches. Each manager is assigned a manger id. Monash Library Services record a managers name and contact phone number. All managers are assigned one particular branch as their home branch.
Monash Library Services maintain records of current loans of books to borrowers.
Each borrower is identified by a borrower number and each copy of a title by a barcode number (the library may have more than one copy of any given title). When a borrower first registers to borrow books the branch where they register is recorded as their home branch. The name and address of each borrower is held so that communications, such as overdue loan reminders, can be sent when necessary.
The information held about a title is its Dewey Decimal call no (20 characters) - this call no is used to identify a particular title and for shelving books. The title, description (1000 characters), author's name/s, publisher's name, publication year, international standard book number (ISBN - a given title may have several ISBN's), purchase price, classification (Reference or Fiction), and the number of pages are recorded. For a Fiction title a reading level is also recorded as an integer from 1 (Easy) to 30 (Very Difficult). A given title may be written by a number of different authors, however the library regards a title as only being published by a single publisher. The library assigns its own unique in-house numerical codes to identify authors and publishers.
A title may cover a number of different subjects, which the library wishes to record so that borrowers can use an online catalogue system to select books by subject as well as title and author's name.

There is a restriction on the number of books a borrower may have on loan at any one time and the loan period. These limits depend on the borrower's classification (Junior, Adult, or Organisation).
Some book copies are placed on counter reserve, and are not available for loan - they may only be used in the library. A flag is added to a book to indicate if it is on counter reserve or not. There may also be other copies of the same title which are available for normal loan.
When a book is borrowed (goes out on loan), the return date is automatically recorded based on the current date and the borrower's classification. A record of all loans which take place is maintained. When a book is returned from a loan its actual return date is recorded. A fine notice is generated and is sent to the borrower if the return date is after the loan due date. In the fine notice, the fine amount will be included1. When the borrower pays the fine, the payment date will be recorded.
Borrowers may reserve books currently out on loan. The date and time on which the reserve was placed is recorded. A given book may be reserved by several borrowers, the book is made available based on the order in which the reserve was placed by the borrower.
When a borrower returns a book, they may if they wish renew their loan and take the book out for a further loan period provided the borrower has not been flagged to prevent further borrowings and the book has not been reserved by another borrower.
A special borrower's status flag is maintained - borrowers who hold overdue books or who have reached their loan limit or who have an unpaid fine, are flagged to prevent further borrowings.
In designing the database, you need to ensure as a minimum that the following operational requirements of the library are met:
a. Allow the catalogue to be searched based on authors, subject category, title, etc
b. Ensure the accuracy on the status of its catalogue, eg which items are on loan,
which books are available, is there any lost items (overdue for more than 3
months)?
c. Manage the loan operations of items in its catalogue, eg who borrowed an item?
Has the item being returned? Is there any fine to be issued due to an overdue loan?
d. Manage the information about its members, eg what is the address of a member? Is
there any fine owed by a member?
e. Manage the information about the branches and their manager.
f. Report usage patterns, such as
i. what items are popular?
ii. what is the average number of items borrowed by a member for a given
time period?
iii. what subject/topic is popular?
iv. which branch has the highest loan activity?
