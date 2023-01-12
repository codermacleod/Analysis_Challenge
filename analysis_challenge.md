# Challenge Analysis Part 2

### Potential Test Areas

- 1. Test sign-up process:
Check that users can sign up successfully, that the sign-up form captures the correct information, and that users receive a confirmation email.
- 2. Test listing a space:
Check that users can list a space successfully, that the listing form captures the correct information (name, description, price per night), and that users can list multiple spaces.
- 3. Test booking a space:
Check that users can successfully book a space for one night, that the booking form captures the correct information (date of stay, number of nights), and that booked nights are not available for other users to book.
- 4. Test approving a booking request:
Check that users can approve booking requests, that the approval process is working correctly, and that users are notified when a booking request is approved.
- 5. Test booking conflicts:
Check that users can't book a space for a night that has already been booked, and that booked nights are not available for other users to book until a booking request has been confirmed.

### Headline Specs & Testing considerations.

- Any signed-up user can list a new space.
    - Ensure when user signs up, they are taken to the **Listing** page and able to create a listed space which is both viewable and accessible by other users.
    
- Users can list multiple spaces.
    - Ensure the spaces page, ‘list a space’ option is always available to users. Check that each space which is listed is viewable and searchable for other users.
    
- Users should be able to name their space, provide a short description of the space, and a price per night.
    - Ensure user can customise their own space name, (with a character limit of 50).
    - Ensure user can write a description (with a character limit of 300).
    - Ensure user can input the price per night (with their desired currency) and that it is viewable to other users.
    
- Users should be able to offer a range of dates where their space is available.
    - Ensure calendar is selectable for desired dates by user who is creating the post.
    - Ensure start and end dates are in chronological order. (Must throw error if not)
    - Ensure:
        - Crossing Time Zones
        - Leap Days
        - Always Invalid Days (Feb 30, Sept 31)
        - Feb 29 in Non-Leap Years
    - Check ability to book multiple date ranges in advance throughout the year(s).
    
- Any signed-up user can request to hire any space for one night, and this should be approved by the user that owns that space.
    - Ensure when a user requests a space for one night, that the owner receives a notification. (Do a mock test with 2 users)
    - Ensure user (requester) is able to view all available spaces.
    - Ensure once space has been confirmed to be used, then space is removed for that particular night.

- Nights for which a space has already been booked should not be available for users to book that space.
    - Test that other users are not able to view and access this particular space.

- Until a user has confirmed a booking request, that space can still be booked for that night.
    - *NOTE: This specification should be reconsidered due to the following issue:
        - Example case scenario:
            - 5 Users are trying to book a lodge in Perthshire.
            - 5 users are filling out the forms for one location.
            - The first person to hit ‘Confirm Booking’ rejects everyone else.
            - This is a very bad user experience for all involved.
        - *Suggestion:
            - Once entered into a booking setup, no other user can access that space for a set period of time (e.g 15 mins).
            

## Login / Sign up Page

---
![LoginSignupPage](https://user-images.githubusercontent.com/73422077/212069799-bf33b9e2-6db4-421e-bd01-ae1f9af4e165.png)

---


### Considerations:

- Test login routes
    - e.g: Biometrics, two-factor authentication
- Test email address validation
- Ensure passwords are not shown while typing

## Book a space

---
![BookSpace](https://user-images.githubusercontent.com/73422077/212069964-c984e5e0-2582-4caf-851a-e9e5c6977710.jpg)

---

### Considerations:

- Test / implement navigation to other pages within site - e.g: Homepage etc..
- Test entire buttons are clickable
    - e.g: When booking a ‘Beautiful Relaxing Space’,(highlighted in blue), you can click on the whole section, not just the arrows.
- Test date fields can be manually inserted or clickable such as the one below:

![calendat](https://user-images.githubusercontent.com/73422077/212070402-5a820429-ce69-4752-a739-3bf111c81212.png)

- Test available dates **are not** greyed out and test that once space has been booked, the date **is** greyed out on the calendar and not selectable.
- Account for things such as:
    - Leap Days
    - Always Invalid Days (Feb 30, Sept 31)
    - Feb 29 in Non-Leap Years
- Ensure ‘List a space’ navigates to the correct page.

## List a space

---
![ListSpace](https://user-images.githubusercontent.com/73422077/212070252-07579243-fc3f-4c7c-b34f-ddd40f7e3b96.jpg)

---

### Considerations:

- Is there a way to navigate back to the homepage?
- Test the name and description fields (highlighted in blue) accept a limited amount of characters. e.g:
    - 30 characters for Name
    - 400 characters for Description
- Displays an output of ‘numbers of character left’ while typing (green). e.g:
    - *‘124 characters remaining’*
- Ensure confirmation image upon clicking *‘List my Space’*
- Test when pressing “Enter” does not activate the *‘List my Space’* accidentally.

## Requests

---

![Requests](https://user-images.githubusercontent.com/73422077/212070594-0070162b-040d-4d01-9f3e-432e6dbe7ce9.png)

---

### Considerations:

- Test / implement navigation to other pages within site - e.g: Homepage etc..
- Requests made are added to ***list of ‘made’*** requests*.*
- Test that upon accepting a ***received request***, status changes to **‘confirmed’.**
- Test that upon a user’s **‘made’** request, that visual/audible confirmation is given back to the user.
- Test upon receiving requests, that buttons “Confirm” and “Deny” (highlighted in blue) are visible to requester.
- Test whether “Other requests for this space” (highlighted in green) are listed.
- Test that entire box (highlighted in orange) is clickable instead of just the arrow.

## Book a night

---

![ChooseNight](https://user-images.githubusercontent.com/73422077/212070678-02f35511-955a-47f7-9b48-c3748e62e55a.jpg)

---

## Considerations:

- Test / implement navigation to other pages within site - e.g: Homepage etc..
- Test the ***start time / end time (e.g Arrive 7pm-7:30pm, Leave by 10:30am next morning)*** of stay is shown to user (for good user experience)
- Test when ‘Request to Book’ (highlighted in blue) is clicked, that a pre-confirmation page is displayed to user with details of booking *(such as time, place, facilities,extra info etc)* before user clicks a ***‘Confirm Night Booking’.***
- Test whether ‘Request to Book’ (highlighted in blue) proceeds to next page if date has not been selected. Ensure pop-up is displayed - advising user to select a date.
- Test that “Enter” does not “Confirm” or “Request” booking - to cover accidental usage by user.
- Again, account for things such as:
    - Leap Days
    - Always Invalid Days (Feb 30, Sept 31)
    - Feb 29 in Non-Leap Years, etc
