# Exercise 1 - Migration Assessment

In this exercise, you will learn how to use the Migration Assessment capability of SAP Integration Suite. This offering helps you estimate the technical efforts involved in the migration process and evaluates how various integration scenarios might be migrated.

## Exercise 1.1 - Launch the Migration Assessment and Checkout the Rules Framework

After completing these steps you will be able to understand what rules the assessment is based on.

1. If you haven't done so, login to the tenant provided to you with your user **userXX** and the credentials provided to you.
      
2. In the SAP Integration Suite landing page, scroll down to **Capabilities**, and select **Create Requests** from the **Assess Migration Scenarios** tile.

<br>![](/exercises/ex1/images/01_01_Assessment_01.png)
   
3. In the Migration Assessment Application, navigate to **Configure > Rules**. Here you can find a list of rules predefined by SAP. Rules are a set of characteristics according to which the application evaluates whether an integration scenario can be migrated and what effort you can expect. As an example, select the rule **SenderAdapterType**.

**Note:** You can’t add custom rules or edit the standard rules. You can only view the standard rules.

<br>![](/exercises/ex1/images/01_01_Assessment_02.png)  

3. Open the variant **MAIN_SenderAdapterType**. Here, you can see all the parameters of the rules, such as Rule Match Value, Assessment Category, and the Weight assigned to each rule match value. Based on these weights, the application calculates the estimated effort, which means that some parameters, and therefore rules, have a bigger influence on the final estimation than others.

<br>![](/exercises/ex1/images/01_01_Assessment_03.png)
  
## Exercise 1.2 - Browse through the Scenario Evaluation Results

In this exercise, you will assess your integration scenarios using the information from the data extraction and evaluation requests. You can access and download analysis of your scenario evaluation runs with details specific to your integration scenarios, for example, adapters and an overview of the rules used in the evaluation. Further, you can download details about the latest evaluation run in one of two formats <b>.xlsx</b> file and <b>.pdf</b> file.

1. Navigate to **Request** and select the **Scenario Evaluation** tile.

<br>![](/exercises/ex1/images/01_01_Assessment_02.png)
   
2. Select the <b>Open Dashboard</b> icon.

<br>![](/exercises/ex1/images/01_01_Assessment_03.png)
   
3. The dashboard shows you an analysis of your scenario evaluation runs with details specific to your integration scenarios, i.e., scenarios grouped by assessment categories, scenarios grouped by rough t-shirt effort estimation, statistics about adapters used in your integration scenarios, statistics about modernization recommendations, etc.

<br>![](/exercises/ex1/images/01_01_Assessment_04.png)
   
4. Switch to the <b>Integration Scenarios</b> tab, and you see the list of all integration scenarios including effort size, assessment category, and number of processed messages in the last 30 days. From here, you can also export the evaluation results into an Excel spreadsheet.

<br>![](/exercises/ex1/images/01_01_Assessment_05.png)
   
5. On the first tab **Full Evaluation Results** of the downloaded Excel file, all integration scenarios are listed with migration effort and status as well as the rules applied to them.

<br>![](/exercises/ex1/images/01_01_Assessment_06.png)

6. On tab **Recommendations**, more details about the modernization recommendations are provided. Instead of pure lift and shift, alternative implementation options are recommended in terms of integration styles, protocols, and security.

<br>![](/exercises/ex1/images/01_01_Assessment_07.png)

7. On tab  **API Recommendations**, API recommendations are listed for an alternative implementation for IDoc messages and BAPIs.

<br>![](/exercises/ex1/images/01_01_Assessment_08.png)

8. Once done with the evaluation, navigate back to the Migration Assessment Application, and switch back to the SAP Integration Suite landing page by clicking on the SAP sign.

<br>![](/exercises/ex1/images/01_01_Assessment_08.png)

## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

Once you have evaluated the migration possibility using the Migration Assessment capability of SAP Integration Suite, you are all set to migrate an integration artifact with the Migration tool.

Continue to - [Exercise 2 - Migrate and test a simple P2P scenario](../ex2/README.md)





