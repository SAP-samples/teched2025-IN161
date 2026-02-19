# Exercise 3 - Extending the Pipeline: Setup Custom Header Properties

In this exercise, we will extend the integration flow we generated previously using the Pipeline's extention points, and set up custom header properties that will allow us to search logs based on payload data.

## Exercise 3.1 - Add Custom Header Properties

1. To add customer header properties, start by navigating to **Integrations and APIs**, open your package **User XX** and select the integration flow **CS_CBR2XX_PIP01_InboundProcessing** flow in the **Artifacts** tab.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_01.png)

2. Click **Edit**.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_02.png)


3. We like to reuse scripts to parse the incoming JSON message and to add the parsed values to the custom header properties. So, let's first import the scripts to the references of your integration flow. Navigate to the **References** tab, click **Add** and select **Script 1.x** from the drop-down-menu.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_03.png)


4. In the pop-up, select the options as follows:

- Source: Integration Flow
- Package: Migration Hands-on Workshop - Solution
- Integration Flow: CS_CBR2SOL_PIP01_InboundProcessing

And for the resources, select the scripts: **addCustomHeaderProperties** and **parseJSON**. Then click **Add**.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_04.png)

5. Now we can see **addCustomHeaderProperties** and **parseJSON** available in the **References** tab.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_05.png)

6. To be able to enhance the integration flow model, we need some space between the last flow step and the end event. Just arrange the two generated flow steps to the left. To add a Script step to the integration flow, click the **Add Flow Step** (plus icon) and then choose **Script>Groovy Script** and place the Script in the integration process.
   To upload the correct script, double-click the script step to launch the properties sheet. And in the **Processing** tab click the **Select** button.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_06.png)

7. In the **Local Resources** tab, choose the **parseJSON** script. Then click **OK**.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_07.png)

8. Back in the **Processing** tab, click the script file we just added to launch the script editor.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_08.png)

9. In the script editor, we can edit the script according to the requirements of the scenario. In the **Problems** tab, we can check for any incompatibilities and recommendations. Note, this step is for display only, you are not supposed to do any changes here. As you can see from the script, the purchase order number, the order date, the item number, the product ID and the category are parsed and stored in the corresponding exchange properties. The details of the Script look good, click **Close** to go back to the Integration Flow.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_09.png)

10. Now, we're repeating the same steps for **addCustomHeaderProperties**: Click **Add Flow Step** (plus icon)...

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_10.png)

11. ... and then choose **Script>Groovy Script** and place the Script in the integration process, next to the first Script.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_11.png)

12. Double-click the script step, click **Select** in the **Processing** tab.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_12.png)

13. Now choose the **addCustomHeaderProperties** script and click **OK**.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_13.png)

14. Click **Save** in the upper corner. And then click **Deploy**.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_14.png)

15. For the Deployment, make sure the correct Runtime Profile is selected, Cloud Integration, and then click **Yes**.

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_15.png)

16. Done!

<br>![](/exercises/ex3/images/03_01_AddCustomHeaderProps_16.png)


## Exercise 3.2 - Test and Monitor

Let's run the integration scenario again, this time with configured custom header properties.

1. Open the Bruno application on your laptop, expand the Migration Exercises collection and select the POST request **Post Item - Notebooks**. Ensure that the right environment is selected in the upper right-corner which defines the host name of the tenant, the client id and the secret. Depending on which tenant you use in the exercises, select either **eu-02a** or **eu-02b**. Then trigger a message by selecting the **Send Request** button right below the environment detail.

<br>![](/exercises/ex3/images/03_02_Test_01.png)

2. The **200 OK** status indicates success!

<br>![](/exercises/ex3/images/03_02_Test_02.png)

3. Navigate back to the monitoring page, and click the **Monitor Message Processing** link below the Artifact Details of your deployed integration flow. In the message monitor, you should see new logs in status **Completed** and the new **Custom Headers**.

<br>![](/exercises/ex3/images/03_02_Test_03.png)


## Summary

You've now added customer header properties to your generated integration scenario. This allows you to search your message logs based on payload data for an improved monitoring and operation.

Continue to - [Exercise 4 - Setup Custom Receiver Determination](../ex4/README.md)
