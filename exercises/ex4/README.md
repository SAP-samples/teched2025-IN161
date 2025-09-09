# Exercise 4 - Extending the Pipeline: Setup Custom Receiver Determination

As an alternative to the standard receiver determination based on an XSLT from the Partner Directory, you can implement your own custom receiver determination. The pipeline for Cloud Integration supports a custom exit that you can use to run your own custom logic without changing the delivered generic integration flows. To do so, you must implement a separate scenario-specific integration flow that's called instead of the standard receiver determination. Furthermore, we need to configure the Partner Directory accordingly to point to the endpoint of the custom integration flow.

In our case, we like to run a message mapping within a custom integration flow instead of the XSLT. Usually, in a migration project you would not replace the XSLT which was generated during the migration because the XSLT fits the routing conditions of the source integration scenario. However, the pipeline for Cloud Integration can also be used for any other scenarios that you newly build on Cloud Integration. So, the intention of this exercise is to show you one of the options to extend the pipeline.

## Exercise 4.1 - Create Custom Integration Flow

First of all, you need to create a custom integration flow which at the end runs to determine the receivers and receiver interfaces. For this, we have shipped a template in the package **Cloud Integration Pipeline - Templates**.

1. Choose the package **Cloud Integration Pipeline - Templates**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_01.png)

2. Click the **Artifacts** tab. As you can see, we do support different templates for implementing custom receiver determination. In our case, we simply use the generic template. Select **Copy** from the **Actions** menu of the integration flow **Pipeline v2 Template Step04 - Custom Receiver Determination**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_02.png)

3. In the upcoming dialog, click **Select** to select the target package.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_03.png)

4. Choose your package **User XX**, with the user number **XX** assigned to you.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_04.png)

5. Edit the template name by entering your user ID number, then click **Copy**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_05.png)

6. In the upcoming dialog, click **Navigate**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_06.png)

7. In your package **User XX**, choose the beforehand copied integration flow **Pipeline v2 Template Step04 - Customer Receiver Determination XX**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_07.png)

8. In the integration flow editor, click **Edit** to switch to the edit mode.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_08.png)

9. To reduce the implementation effort during the exercises, we will reuse a message mapping. In the Integration Flow Properties, click the **References** tab, and switch to the **Global** tab. Choose **Message Mapping** under the drop-down bar of **Add References**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_09.png)

10. In the upcoming dialog, choose **Migration Hands-on Workshop - Solution**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_10.png)

11. Two message mappings should be displayed. Choose **mm_item_to_receivers_sol**. Then, click **OK**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_11.png)

12. As you can see, the message mapping **mm_item_to_receivers_sol** has been added to the references of your integration flow.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_12.png)

13. Now, let's add the message mapping to the integration flow model. Select the message start event **Start**, and click the **+** (plus) button from the quick menu.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_13.png)

14. Search for **Mapping** under All Steps. Choose **Message Mapping**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_14.png)

15. Select the added message mapping flow step, and click on the **Assign** icon from the quick menu to select the message resource.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_15.png)

16. In the upcoming dialog, switch to the **Global Resources** tab, and choose **mm_item_to_receivers_sol**. Then, click **OK**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_16.png)

17. The message mapping should be added. Let's check the mapping logic to understand the routing definitions. Under Message Mapping, switch to the **Processing** tab, and select the **/mm_item_to_receivers_sol** link.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_17.png)

18. The message mapping editor should open in a new browser tab. Click the **Receiver** node of the target structure to open its field mapping. As you can see, a user defined mapping function is used to define the routing conditions based on the source node **Category**. Select the **Read Script** icon of the user defined mapping function **getReceiverList**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_18.png)

19. From the Function Definition, you can see that the routing differs from the one in the generated XSLT. Here, messages with category **Software** are sent to the receivers **XYZ200** and **XYZ201**, messages with category **Notebooks** are sent to **XYZ201** and **XYZ202**, and messages with category **Keyboards** are sent to all three receivers. Click **Close** to close the script editor.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_19.png)

20. Expand the **ReceiverNotDetermined** node. From here you can see the behavior if no receiver could be determined. So for any other category, the messages are sent to the default receiver **XYZ200**. You can close the browser tab and navigate back to the integration flow editor.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_20.png)

21. In the integration flow editor, click **Save**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_21.png)

22. Next, we need to configure the endpoint of the custom integration flow. You need to click **Cancel** to be able to configure your integration flow.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_22.png)

23. Click **Configure**. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_23.png)

24. In the configuration dialog, enter the Address **/CS_CBR2XX/pip04/CustomReceiverDetermination** with **XX** the user ID assigned to you, then click **Save**, and **Deploy**.

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_24.png)

25. Check Deployment Status and Runtime Status: **Started**. Confirm your flow is successfully deployed. 

<br>![](/exercises/ex4/images/04_01_CreateIntegrationFlow_25.png)


## Exercise 4.2 - Configure the Partner Directory

Now that the custom integration flow has been successfully deployed, we need to configure the configuration scenario in the Partner Directory to enable the custom receiver determination.

1. Choose **Integrations and APIs** under **Monitor**. Click the **Partner Directory** tile. 

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_01.png)

2. In the Partner Directory UI, search for your number, and choose your configuration scenario **CS_CBR2XX**. On the **String Parameters** tab, click **Create**.

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_02.png)

3. Create a new String Parameter with ID: **CustomXRDEndpoint** and Value: **/CS_CBR2XX/pip04/CustomReceiverDetermination**. Note, the value needs to be identical to the endpoint chosen above. Then, click **Create**.

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_03.png)

4. As you can see, a new String Parameter has been added.

<br>![](/exercises/ex4/images/04_02_PartnerDirectory_04.png)

## Exercise 4.3 - Test and Monitor

Let's run the integration scenario again, this time with the custom receiver determination.

1. Open the Bruno application on your laptop, expand the Migration Exercises collection and select the POST request **Post Item - Keyboards**. Ensure that the right environment is selected in the upper right-corner. Depending on which tenant you use in the exercises, select either **eu-02a** or **eu-02b**.  Then trigger a message by selecting the **Send Request** button right below the environment detail.

<br>![](/exercises/ex4/images/04_03_Test_01.png)

2. The **200 OK** status indicates success!

<br>![](/exercises/ex4/images/04_03_Test_02.png)

3. Navigate back to the **Message Status Overview**. Change the **Overview By** to **Senders**. This provides you an overview of all processed messages grouped by the sender system. Click the **Completed** or **Total** number link that corresponds to the sender **CBR2XX** with the user number **XX** assigned to you.

<br>![](/exercises/ex4/images/04_03_Test_03.png)

4. In the upcoming message monitor, you should see couple of new logs in status Completed. The log of the integration flow **Pipeline v2 Generic Step02 - Integrated Messaging Runtime Asyncthe** indicates that message were sent to receivers **XYZ201**, **XYZ202**, and **XYZ200**. 

<br>![](/exercises/ex4/images/04_03_Test_04.png)

5. In the Bruno test client, you may resend different requests and check the monitoring. If you select the last request with the category **NONE** that doesn't exist in the XPath conditions, the receiver not determined path should be carried out.

<br>![](/exercises/ex4/images/04_03_Test_05.png)

6. Navigate back to the message monitor. In the message monitor, you should see that the receiver is **XYZ200**, Customer Status: **ReceiverNotFoundDefault**, and the category value: **NONE**.

<br>![](/exercises/ex4/images/04_03_Test_06.png)


## Summary

You've now learned how to setup custom receiver determination for the Pipline for Cloud Integration.

Congratulations. You have completed all exercises.
