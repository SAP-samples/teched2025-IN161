# Exercise 4 - Extending the Pipeline: Setup Custom Receiver Determination

In this exercise, we will create...

## Exercise 4.1 - Create Custom Integration Flow

After completing these steps you will have created...

1. Choose **Cloud Integration Pipeline - Templates**

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_01.png)

2. Click the **Artifacts** tab. Choose **Pipeline v2 Template Step04 - Custom Receiver Determination**. Click on the dots and choose **copy**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_02.png)

3. Click **Select**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_03.png)

4. Choose **User XX**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_04.png)

5. Edit the template name and package by entering your user ID number, then click **Copy**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_05.png)

6. Click **Navigate**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_06.png)

7. In **User XX**, choose **Pipeline v2 Template Step04 - Customer Receiver Determication XX**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_07.png)

8. Click **Edit**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_08.png)

9. Under Intergration Flow, click **References** tab, and click **Global (0)** tab. Choose **Message Mapping** under the drop-down bar of **Add References**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_09.png)

10. Choose **Migration Hands-on Workshop - Solution**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_10.png)

11. Choose **mm_item_to_receivers_sol**.Click **OK**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_11.png)

12. Choose **mm_item_to_receivers_sol**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_12.png)

13. Click the + button.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_13.png)

14. Search for **Mapping** under All Steps. Choose **Message Mapping**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_14.png)

15. Click on ✓ to select message resource.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_15.png)

16. Click **Global Resources**, and choose **mm_item_to_receivers_sol**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_16.png)

17. Under Message Mapping, click **Processing**, and click **/mm_item_to_receivers_sol**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_17.png)

18. Click Categotry > Receiver. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_18.png)

19. Click **Close**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_19.png)

20. Under Mapping Expression, choose **XYZ200**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_20.png)

21. Click **Save**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_21.png)

22. Click **Cancel**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_22.png)

23. Click **Configure**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_23.png)

24. Enter Address **ICS_CBR2XX/pip04/CustomReceiverDetermination**, then click **Save**, and **Deploy**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_24.png)

25. Check Deployment Status and Runtime Status: Started. Confirm your flow is successfully deployed. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_25.png)


## Exercise 4.2 - Configure the Partner Directory

After completing these steps you will have...

1. Choose **Integrations and APIs** under Monitor. Click **Partner Directory**. 

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_01.png)

2. In Partners, search for your number, and choose **CS_CBR2XX**. Click **Create**.

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_02.png)

3. Create String Parameter with ID: **CustomXRDEndpoint** and Value:**ICS_CBR2XX/pip04/CustomReceiverDetermination**.

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_03.png)

4. Confirm String Parameter with ID: **CustomXRDEndpoint** and Value:**ICS_CBR2XX/pip04/CustomReceiverDetermination**.

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_04.png)

## Exercise 4.3 - Test and Monitor

After completing these steps you will have...

1. Open the Bruno application on your laptop, expand the Migration Exercises collection and select the POST request **Post Item - Keyboards**. Ensure that the **eu-02a** environment has been selected in the upper right-corner. Then trigger a message by selecting the Send Request button right below the environment detail.

<br>![](/exercises/ex4/images/04_03_Test_01.png)

2. The **200 OK** status indicates success!

<br>![](/exercises/ex4/images/04_03_Test_02.png)

3. In the **Message Status Overview**, change the **Overview By** to **Senders**. This provides you an overview of all processed messages grouped by the sender system. Click the **Completed** or **Total** number link that corresponds to the sender **CBR2XX** with the user number **XX** assigned to you.

<br>![](/exercises/ex4/images/04_03_Test_03.png)

4. In the upcoming message monitor, you should see five new logs in status Completed. For **Pipeline v2 Generic Step02 - Integrated Messaging Runtime Asyncthe** message should be sent to receiver **XYZ201**, **XYZ202**, **XYZ200**. 

<br>![](/exercises/ex4/images/04_03_Test_04.png)

5. In the Bruno test client, you may resend different requests and check the monitoring. If you select the last request with the category **NONE** that doesn't exist in the XPath conditions, the receiver not determined path should be carried out.

<br>![](/exercises/ex4/images/04_03_Test_05.png)

6. Navigate back to the message monitor. In the message monitor, you should see receiver is **XYZ200**, Customer Status: **ReceiverNotFoundDefault**, and the category value: **NONE**.
<br>![](/exercises/ex4/images/04_03_Test_06.png)


## Summary

You've now ...

Congratulations. You have completed all exercises.
