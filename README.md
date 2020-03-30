# Description

If your AWS account has "must MFA" access then typically you can't do much from the CLI until you get temporary credentials from STS.

# Contents

## `awsmfa-fetch`

This is the main script that will talk to the endpoints, discover your account, what MFA token is assigned, request the credentials and allow them to be exported. Typically you would do something like:
```
    eval $(AWS_PROFILE=myprofile awsmfa-fetch)
```

## `awsmfa`

This is a simple function that unsets the main AWS variables and then calls the `eval` command:
```
awsmfa myprofile
```

## `awsmfa-clear`
Just unsets the main AWS variables.


# Example usage

```
% getaws gcsf
You are: sweharris
Your MFA device is: arn:aws:iam::123456789012:mfa/sweharris
Enter your MFA code now: 299255
Keys valid until 2017-11-04T02:12:13Z
```
