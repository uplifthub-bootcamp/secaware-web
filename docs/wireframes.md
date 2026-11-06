# Website wireframes

These show what goes on each page and where, not how it should look. Every page that loads data also needs a loading state and an error state.

## Learner pages

### Course catalogue: `/`

```text
+----------------------------------------------------------+
| SecAware                 Courses   Log in   Sign up      |
+----------------------------------------------------------+
| Short courses on staying safe online                     |
|                                                          |
| +----------------------+  +----------------------+       |
| | Passwords and 2FA    |  | Phishing and scams   |       |
| | Make your accounts   |  | Spot a fake message  |       |
| | harder to break into |  | before you click     |       |
| | 3 lessons            |  | 3 lessons            |       |
| +----------------------+  +----------------------+       |
+----------------------------------------------------------+
Empty state: "No courses yet. Please check back soon."
```

### Sign up and log in

```text
+-------------------------------+   +-------------------------------+
| Create your account           |   | Log in                        |
|                               |   |                               |
| Name      [                 ] |   | Email     [                 ] |
| Email     [                 ] |   | Password  [                 ] |
| ! Enter a valid email address |   |                               |
| Password  [                 ] |   | ! Email or password is wrong  |
| At least 15 characters        |   |                               |
|                               |   | [ Log in ]                    |
| [ Create account ]            |   | New here? Sign up             |
| Have an account? Log in       |   +-------------------------------+
+-------------------------------+
```

Field errors sit under their field and come from `error.fields`.

### Course page and lesson reader

```text
+-------------------------------+   +-------------------------------+
| Passwords and 2FA             |   | Lesson 1 of 3                 |
| Make your accounts much       |   | Why passwords get stolen      |
| harder to break into.         |   |                               |
|                               |   | It is rarely a lucky guess    |
| 1 of 3 lessons complete       |   | Many stolen passwords come    |
|                               |   | from another site's breach.   |
| [x] Why passwords get stolen  |   |                               |
| [ ] Make strong passwords     |   | +---------------------------+ |
| [ ] Turn on 2FA               |   | | Tip: use a different      | |
|                               |   | | password on every site.   | |
| [ Continue ]  [ Take the quiz]|   | +---------------------------+ |
+-------------------------------+   |                               |
                                    | [ Mark complete and continue ]|
                                    +-------------------------------+
```

Visitors who are not logged in can read lessons. Marking one complete or taking the quiz sends them to log in first.

### Quiz and result

```text
+-------------------------------+   +-------------------------------+
| Passwords and 2FA: quiz       |   | You passed: 80%               |
| You need 70% to pass.         |   | You needed 70%.               |
|                               |   |                               |
| 1. What should you do if a    |   | 1. Correct                    |
|    site has a data breach?    |   | 2. Not quite                  |
| ( ) Change that password...   |   | 3. Correct                    |
| ( ) Nothing, unless money...  |   |                               |
|                               |   | [ View your certificate ]     |
| 2. ...                        |   | [ Back to course ]            |
|                               |   +-------------------------------+
| [ Submit answers ]            |   If they did not pass, replace the
+-------------------------------+   certificate link with [ Try again ].
```

### Dashboard and certificate

```text
+-------------------------------+   +-------------------------------+
| Hello, Test Learner           |   |    Certificate of completion  |
|                               |   |                               |
| My courses                    |   |    Test Learner               |
| Passwords and 2FA  2 of 3     |   |    completed                  |
|                               |   |    Passwords and 2FA          |
| My certificates               |   |    6 November 2026            |
| Passwords and 2FA      [View] |   |                               |
+-------------------------------+   |    Check it at:               |
                                    |    /verify/7F3A9C21B04E6D18   |
                                    |                               |
                                    |    [ Print ]                  |
                                    +-------------------------------+
```

The verification page is public. It shows the same certificate, or "We could not find that certificate" for an unknown code.

## Admin pages

These show only to admin accounts. The API still has to refuse learners, because anyone can open any page or call the API directly.

```text
+-------------------------------+   +-------------------------------+
| Admin: courses   [ New course]|   | Edit: Passwords and 2FA       |
|                               |   | Title     [                 ] |
| Passwords and 2FA  Published  |   | Summary   [                 ] |
| Phishing and scams Draft      |   | Pass mark [ 70 ]              |
| Device safety      Draft      |   | [ Save ]  [ Publish ]         |
+-------------------------------+   |                               |
                                    | Lessons            [ Add ]    |
                                    | 1. Why passwords get stolen   |
                                    |                               |
                                    | Questions          [ Add ]    |
                                    | 1. What should you do if...   |
                                    +-------------------------------+
```

```text
+-------------------------------+   +-------------------------------+
| Edit lesson                   |   | Edit question                 |
| Title    [                  ] |   | Prompt   [                  ] |
|                               |   |                               |
| [Heading  v] [              ] |   | (o) [ Change that password  ] |
| [Paragraph v][              ] |   | ( ) [ Nothing               ] |
| [Tip      v] [              ] |   | [ Add an option ]             |
| [ Add a block ]               |   |                               |
| [ Save ]                      |   | [ Save ]                      |
+-------------------------------+   +-------------------------------+
```
