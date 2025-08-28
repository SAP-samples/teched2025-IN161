# Prepare the Migration Exercises

After having finished the assessment of the current SAP Process Orchestration landscape, the next step is the actual migration.

Before running through the migration tool exercises, you first need to run trough the following preparation steps:
- [Create an integration package](#create-an-integration-package)
- [Setup Bruno API client](#setup-bruno-api-client)

## Create an Integration package

As a prerequisite, you first need to create an integration package where the automatically generated integration flows are created. If you have already run through other exercises before, you may have already created an own package. In this case, you can simply reuse the other package and skip the steps below.

1. Open the SAP Integration Suite landing page, and navigate to <b>Design > Integrations and APIs</b>, and select  <b>Create</b>.

<br>![](/exercises/ex0/images/00_01_Package_01.png)
   
2. Fill in the <b>Name</b> of the integration package, e.g. **User XX** where <b>XX</b> is the user number assigned to you ranging from 00 to 99, and a short <b>Description</b>. The technical name is automatically set. Then click <b>Save</b>.

<br>![](/exercises/ex0/images/00_01_Package_02.png)

## Setup Bruno API client

To run the integration scenarios, we use the open source API client Bruno for which we have prepared a collection. The collection contains sample requests and environment parameters to authenticate at the provided tenant.

### Import collection

Import the provided collection if not already done.

1. In the SAP Integration Suite landing page, navigate to **Design > Integrations and APIs**. Select the integration package **Migration Hands-on Workshop - Solution** and switch to tab **Documents**. From there you can download the Bruno collection **Migration Hands-on Workshop**. The downloaded file is zipped, so you first need to unzip the file in your download folder before proceeding.

<br>![](/exercises/ex0/images/00_02_Bruno_00.png)

2. Open Bruno and select **Import Collection** either from the menu or from the home screen.

<br>![](/exercises/ex0/images/00_02_Bruno_01.png)

3. On the upcoming dialog, select the type **Bruno Collection**.

<br>![](/exercises/ex0/images/00_02_Bruno_02.png)

4. Navigate to the location where you saved and unzippd the beforehand downloaded collection and select the file **Migration Hands-on Workshop.json**.

<br>![](/exercises/ex0/images/00_02_Bruno_03.png)

5. Browse to define a location, eventually create a new folder. Then select **Import**.

<br>![](/exercises/ex0/images/00_02_Bruno_04.png)

### Configure the Bruno client

As part of the collection, variables and environment parameters have been maintained, that is **host** of the Cloud Integration tenant runtime, **client id** and **client secret** to be able to authenticate at the Cloud Integration tenant, and the variable **participant** holding the user number assigned to you.

1. Navigate to the **Settings** of the beforehand imported collection.

<br>![](/exercises/ex0/images/00_02_Bruno_05.png)

2. Switch to tab **Vars** and change the value of the variable **participant**. Replace **XX** with the user number assigned to you ranging from 01 to 99. Then **Save** your changes.

<br>![](/exercises/ex0/images/00_02_Bruno_06.png)

3. If you expand the **Migration Hands-on Workshop** collection, you should see four requests. In order to be able to select an environment, you need to select any request. As you can see, the variables are used to define the URL and the authentication. Select either the environment **eu-02a** or **eu-02b** depending on the tenant used in the exercises. The instructors will let you know which environment is used.

<br>![](/exercises/ex0/images/00_02_Bruno_07.png)

## Summary

Now that you have run through the preparation steps, you can start with the actual migration exercise.

Go back to - [Main page](../../README.md)
