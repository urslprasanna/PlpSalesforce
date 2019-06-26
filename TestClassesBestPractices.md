#### Please follow below salesforce Best Practice for Test Classes:-

1. Test class must start with _@isTest_ annotation if class class version is more than 25
2. Test environment support _@testVisible_, _@testSetup_ as well
3. Unit test is to test particular piece of code working properly or not.
4. Unit test method takes no argument, send no email, commit no data to database and flagged with testMethod keyword.
5. To deploy to production at least 75% code coverage is required 
6. Test method and test classes are not counted as a part of code limit
7. System.debug statement are not counted as a part of apex code limit.
8. We should not focus on the  percentage of code coverage, we should make sure that every use case should covered including positive, negative, bulk and single record.

   **Single Action** - To verify that the the single record produces the correct an expected result.
   
   **Bulk action** - Any apex record trigger ,class or extension must be invoked for 1-200 records.
   
   **Positive behavior:** Test every expected behavior occurs through every expected permutation, i.e., user filled out every correctly data and not go past the limit.
   
   **Negative Testcase:** Not to add future date, Not to specify negative amount.
   
   **Restricted User:** Test whether a user with restricted access used in your code.
9. Test class should be annotated with _@isTest_.
10. _@isTest_ annotation with test method  is equivalent to testMethod keyword.
11. Test method should static and no void return type.
12. Test class and method default access is private, no matter to add access specifier.
13. Classes with _@isTest_ annotation can't be a interface or enum.
14. Test method code can't be invoked by non test request.
15. Stating with salesforce API 28.0 test method can not reside inside non test classes.
16. _@Testvisible_ annotation to make visible private methods inside test classes.
17. Test method can't be used to test web-service call out. Please use call out mock.
18. You can't  send email from test method.
19.User, profile, organization, AsyncApexjob, Corntrigger, RecordType, ApexClass, ApexComponent, ApexPage we can access without (seeAllData=true).
20. SeeAllData=true will not work for API 23 version eailer.
21. Accessing static resource test records in test class e,g List<Account> accList=Test.loadData(Account,SobjectType,'ResourceName').
22. Create TestFactory class with @isTest annotation to exclude from organization code size limit.
23. @testSetup to create test records once in a method  and use in every test method in the test class.
24. We can run unit test by using Salesforce Standard UI,Force.com IDE ,Console ,API.
25. As apex runs in system mode so the permission and record sharing are not taken into account . So we need to use system.runAs to enforce record sharing.
26. System.runAs will not enforce user permission or field level permission.
27. Every test to runAs count against the total number of DML issued in the process.
