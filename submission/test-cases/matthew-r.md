# Test Cases: [Your First Name Last Initial]

**Team number:** [XX]

<!--
HOW TO USE THIS FILE
1. Copy this file. Name the copy with your first name and last initial, like  maria-g.md
2. Leave TEMPLATE.md untouched for your teammates.
3. Write at least ONE failing test case. More is better.
4. Copy the block between the lines for each new test case.
5. Test IDs: use your initials plus a number, like  MG-01, MG-02. This keeps IDs unique across your team.
6. See docs/TESTING_FIELD_GUIDE.md for the sample test case TC-00.
-->

---

**Test ID:**
**Written by:**
**Title:**
**Traces to:**
**Test type:** (Unit / Integration / System / Acceptance / Boundary Value / Negative / Security)
**Preconditions:**
**Test data:**

**Steps:**
1.
2.
3.

**Expected result:**
**Actual result:**
**Status:** (Pass / Fail)
**Severity:** (Critical / Major / Minor, Fail only)
**V or V:** (Verification / Validation, Fail only)

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
**Title:** Description field limits the maximum number of characters  
**Traces to:** Costume submission form  
**Test type:** Boundary Value  
**Preconditions:** The user is logged in and is submitting a costume.  
**Test data:** A description longer than the allowed limit.

**Steps:**
1. Enter a description longer than the expected maximum length.
2. Complete the remaining required fields.
3. Click “Submit Costume.”

**Expected result:** The description is limited to the maximum length or the submission is rejected.  
**Actual result:** The description box accepts an unlimited number of characters.  
**Status:** Fail  
**Severity:** Minor  
**V or V:** Verification

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