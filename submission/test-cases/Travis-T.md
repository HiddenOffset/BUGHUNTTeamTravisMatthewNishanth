# Test Cases: [Travis, Matthew, Nishanth]

**Team number:** [15]

---

**Test ID:** TC-01  
**Written by:** [Matthew]  
**Title:** Deleted costume restores the vote used on it  
**Traces to:** Voting workflow  
**Test type:** Integration  
**Preconditions:** A logged-in user has used all four votes. At least one voted costume exists.  
**Test data:** User account with 4 votes; existing costume.

**Steps:**
1. Log in.
2. Vote on a costume until all four votes are used.
3. Delete one of the costumes that received a vote.
4. Check the user’s remaining votes.

**Expected result:** The vote used on the deleted costume is returned to the user.  
**Actual result:** The user does not receive the vote back.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Validation

---

**Test ID:** TC-02  
**Written by:** [Matthew]  
**Title:** Submit Costume rejects a costume without a name  
**Traces to:** Costume submission form  
**Test type:** Negative  
**Preconditions:** The user is logged in and is on the costume submission page.  
**Test data:** Name: empty; Description: “Test costume”; Category: Classic.

**Steps:**
1. Leave the costume name empty.
2. Enter a description and select a category.
3. Click “Submit Costume.”

**Expected result:** The app rejects the submission and displays a required-name error.  
**Actual result:** The app accepts the costume without a name.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Validation

---

**Test ID:** TC-03  
**Written by:** [Matthew]  
**Title:** Description text box should not expand infinitely  
**Traces to:** Costume submission form  
**Test type:** Boundary Value  
**Preconditions:** The user is logged in and is on the costume submission page.  
**Test data:** A description text box.

**Steps:**
1. Locate the description text box.
2. Drag the bottom-right corner of the text box.
3. Continue expanding the text box as far as possible.

**Expected result:** The description text box remains within a reasonable fixed size or has a maximum width and height.  
**Actual result:** The description text box can be expanded infinitely by dragging the bottom-right corner.  
**Status:** Fail  
**Severity:** Minor  
**V or V:** Validation

---

**Test ID:** TC-04  
**Written by:** [Matthew]  
**Title:** Duplicate costumes are rejected  
**Traces to:** Costume submission workflow  
**Test type:** Negative  
**Preconditions:** A costume already exists in the app. The user is logged in.  
**Test data:** A second costume with the same name, description, and category.

**Steps:**
1. Submit a costume.
2. Submit another costume with the same information.
3. Check the costume list.

**Expected result:** The duplicate costume is rejected or the user receives a duplicate-costume error.  
**Actual result:** The app accepts the duplicated costume.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Validation

---

**Test ID:** TC-05  
**Written by:** [Matthew]  
**Title:** Login form clears the password and username fields after login  
**Traces to:** Login workflow  
**Test type:** System  
**Preconditions:** A registered account exists.  
**Test data:** Valid username and password.

**Steps:**
1. Enter a valid username and password.
2. Click “Login.”
3. Check the username and password fields.

**Expected result:** The user is logged in and the login fields are cleared.  
**Actual result:** The username and password remain visible in the fields.  
**Status:** Fail  
**Severity:** Minor  
**V or V:** Validation

---

**Test ID:** TC-06  
**Written by:** [Matthew]  
**Title:** Only logged-in users can vote  
**Traces to:** Voting workflow  
**Test type:** Security  
**Preconditions:** The user is logged out and costumes are visible.  
**Test data:** An available costume.

**Steps:**
1. Log out.
2. Open the voting page.
3. Click the vote button on a costume.

**Expected result:** The app prevents voting and asks the user to log in.  
**Actual result:** The logged-out user can vote.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Verification

---

**Test ID:** TC-07  
**Written by:** [Matthew]  
**Title:** User cannot vote after using all four votes  
**Traces to:** Voting workflow  
**Test type:** Boundary Value  
**Preconditions:** The user is logged in and has four available votes.  
**Test data:** Five available costumes.

**Steps:**
1. Vote on four different costumes.
2. Attempt to vote on a fifth costume.
3. Check the remaining vote count.

**Expected result:** The first four votes succeed, the fifth vote is rejected, and the vote count remains zero.  
**Actual result:** The user can vote again and the vote count becomes negative one.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Verification

---

**Test ID:** TC-08  
**Written by:** [Matthew]  
**Title:** Logging out and back in preserves the correct vote count  
**Traces to:** Authentication and voting state workflow  
**Test type:** Integration  
**Preconditions:** A logged-in user has used all four votes.  
**Test data:** User account with zero remaining votes.

**Steps:**
1. Use all four votes.
2. Log out.
3. Log back in.
4. Check the remaining vote count.

**Expected result:** The user’s vote count remains zero.  
**Actual result:** The vote count is reset, and the user receives another vote.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Verification

---

**Test ID:** TC-09  
**Written by:** [Matthew]  
**Title:** Username has a maximum character limit  
**Traces to:** Registration form  
**Test type:** Boundary Value  
**Preconditions:** The registration page is open.  
**Test data:** Username longer than the expected maximum length.

**Steps:**
1. Enter a username longer than the allowed limit.
2. Enter valid registration information.
3. Submit the registration form.

**Expected result:** The registration is rejected with a username-length error.  
**Actual result:** The app accepts a username with no character limit.  
**Status:** Fail  
**Severity:** Minor  
**V or V:** Verification

---

**Test ID:** TC-10  
**Written by:** [Matthew]  
**Title:** Registration rejects spaces, special characters, and unsupported symbols  
**Traces to:** Registration form  
**Test type:** Negative  
**Preconditions:** The registration page is open.  
**Test data:** Usernames containing spaces, special characters, and Egyptian hieroglyphs.

**Steps:**
1. Enter a username containing unsupported characters.
2. Enter a valid password.
3. Submit the registration form.

**Expected result:** The app rejects the username and explains which characters are allowed.  
**Actual result:** The app accepts spaces, special characters, and Egyptian hieroglyphs.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Verification

---

**Test ID:** TC-11  
**Written by:** [Matthew]  
**Title:** Leaderboard works when only one costume exists  
**Traces to:** Leaderboard workflow  
**Test type:** Acceptance  
**Preconditions:** The app contains exactly one costume.  
**Test data:** One submitted costume.

**Steps:**
1. Open the leaderboard.
2. Check the displayed results.
3. Refresh the page if necessary.

**Expected result:** The leaderboard displays the single costume and its ranking.  
**Actual result:** The leaderboard does not function when only one costume exists.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Validation

---

**Test ID:** TC-12  
**Written by:** [Matthew]  
**Title:** Creative costumes appear in the voting tab  
**Traces to:** Costume category and voting workflow  
**Test type:** System  
**Preconditions:** At least one costume exists under the Creative category.  
**Test data:** Creative-category costume.

**Steps:**
1. Submit or locate a Creative-category costume.
2. Open the voting tab.
3. Search for the Creative costume.

**Expected result:** Creative costumes appear in the voting tab.  
**Actual result:** Creative costumes do not appear in the voting tab.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Validation

---

**Test ID:** TC-13  
**Written by:** [Matthew]  
**Title:** Delete costume works after disabling the browser confirmation prompt  
**Traces to:** Costume deletion workflow  
**Test type:** Integration  
**Preconditions:** A deletable costume exists. The browser confirmation dialog has been disabled or dismissed.  
**Test data:** Existing costume.

**Steps:**
1. Open the costume options.
2. Select “Delete.”
3. Disable or dismiss the browser confirmation prompt.
4. Try to delete the costume again.

**Expected result:** The app still provides a working deletion method or safely completes the deletion.  
**Actual result:** The delete button does not work after the confirmation prompt is disabled.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Validation

---

**Test ID:** TC-14  
**Written by:** [Matthew]  
**Title:** Users can vote on costumes in the Creative category  
**Traces to:** Voting workflow  
**Test type:** Acceptance  
**Preconditions:** A Creative-category costume is visible to the user. The user is logged in and has an available vote.  
**Test data:** Creative-category costume.

**Steps:**
1. Log in.
2. Open the Creative category or voting tab.
3. Click the vote button for a Creative costume.

**Expected result:** The vote is recorded and the user’s remaining vote count decreases by one.  
**Actual result:** The user cannot vote on Creative-category costumes.  
**Status:** Fail  
**Severity:** Major  
**V or V:** Validation
