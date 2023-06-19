<h2>Report</h2>

<ol>
    <li>
        <h4>Problem definition:</h4>                    
        The objective is to predict whether or not a passenger survived the Titanic accident based on certain characteristics:Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked.<br>
    </li>
    <li>
        <h4>Collecting and preparing the data:</h4>       
        The dataset containing information about Titanic passengers such as age, gender, passenger class, ticket price, etc. has been taken from the website: kaggle.com/competitions/titanic.
        <a href="https://www.kaggle.com/competitions/titanic" target="_blank">kaggle.com/competitions/titanic</a>.<br>
        Data preparation, performing tasks such as cleaning, handling missing values and coding categorical variables.<br><br>
        <ul>
            <li>
                Data: train.csv
            </li>                          
            <li>  
                There is no duplicate data.
            </li>    
            <li> 
                Embarked field had 2 null fields the mode was taken and the value equal to S was found.
            </li>            
            <li>
                Removal of non-numeric values: 'Name', 'Sex', 'Ticket', 'Cabin', 'Embarked'
            </li>                          
                <ul>
                    <li>
                    Classification of crew and passengers was analyzed by Survived, Pclass, Age.
                    </li>
                    <li>
                    The following columns have been removed from the dataframe:
                        <ol>
                            <li>
                            Name: Type is object
                            </li>
                            <li>
                            Ticket: No pattern found in the data.
                            </li>
                            <li>
                            Cabin: 787 null values.
                            </li>
                        </ol>
                    </li>
                </ul>
            </li>                    
            <li> 
                Number of null fields in 'Age': <b>177</b> of 891<br>
                5+16+2+7+9+85+9+2+25+17 = <b>177</b>
            </li>
            <li> 
                AVERAGE was made to fill in these fields, the averages were found using the following criteria: Survived, Gender, Age Group and Pclass.<br>
                <ol>
                    <li>
                    There were <b>5</b> valueless records for first class male survivor. The average age of the first class male survivor was 36.2 goes to 35.1 with the removal of the outlier.
                    </li>
                    <li>
                    There were <b>16</b> valueless records for non-surviving first class male<br>
                    Normal average was used: 44.5
                    </li>
                    <li>
                    There were <b>2</b> valueless records for second class male survivor<br>
                    Normal average was used: 16 
                    </li>
                    <li>
                    There were <b>7</b> valueless records for second class male non-survivor<br>
                    Normal average was used: 33.3
                    </li>
                    <li>
                    There were <b>9</b> valueless records for third class male survivor<br>
                    Normal average was used: 22.2
                    </li>
                    <li>
                    There were <b>85</b> valueless records for non-surviving third class male<br>
                    Normal average was used: 27.2
                    </li>
                    <li>
                    There were <b>9</b> valueless records for first class female survivor<br>
                    Normal average was used: 34.9
                    </li>
                    <li>
                    There were <b>2</b> valueless records for second class female survivor<br>
                    Normal media was used: 28.8
                    </li>
                    <li>
                    There were <b>25</b> valueless records for third class female survivor<br>
                    Normal average was used: 19.3
                    </li>
                    <li>
                    There were <b>17</b> valueless records for third class female survivor<br>
                    Normal average was used: 23.8
                    </li>
                </ol>
            </li>
        </ul>
        <br>
        <ul>
            <li>
                Data: test.csv
            </li>                         
            <li>  
            There is an empty value in the Fare column. <br>
            The average was taken to fill it.<br>
            Fare: 35.63 £
            </li>                             
            <li> 
                Number of null fields in 'Age': <b>86</b> of 418<br>
                7+4+50+2+1+22 = <b>86</b>
            </li>
            <li> 
                AVERAGE was made to fill in these fields, the averages were found using the following criteria: Gender, Age Group and Class P.<br>
                <ol>
                    <li>
                    There were <b>7</b> valueless records for first class male<br>
                    Normal average was used: 40.5 
                    </li>
                    <li>
                    There were <b>4</b> valueless records for second class male<br>
                    Normal average was used: 27.0
                    </li>
                    <li>
                    There were <b>50</b> valueless records for third class male<br>
                    Normal average was used: 22.2
                    </li>
                    <li>
                    There were in total 61 valueless records for male<br>
                    Normal average was used: 22.2
                    </li>       
                    <li>
                    There were <b>2</b> valueless records for first class female<br>
                    Normal average was used: 41.3
                    </li>
                    <li>
                    There were <b>1</b> valueless records for second class female<br>
                    Normal media was used: 24.3
                    </li>
                    <li>
                    There were <b>22</b> valueless records for third class female<br>
                    Normal average was used: 19.3
                    </li>
                    <li>
                    There were in total 25 valueless records for female<br>
                    Normal average was used: 23.0
                    </li>                            
                </ol>
            </li>
        </ul>
        <br>
        <ul>
            <li>
                After removing the non-numeric fields and filling in the null fields, the accuracy was calculated<br>
                <h4>Algorithms</h4>
                <table>
                    <tr>
                        <th>Model</th>
                        <th>Accuracy</th>
                    </tr>
                    <tr>
                        <td>DecisionTreeClassifier</td>
                        <td>0.6425</td>
                    </tr>
                    <tr>
                        <td>KNeighborsClassifier n_neighbors=3</td>
                        <td>0.8324</td>
                    </tr>
                    <tr>
                        <td>KNeighborsClassifier n_neighbors=5</td>
                        <td>0.8212</td>
                    </tr>
                    <tr>
                        <td>KNeighborsClassifier n_neighbors=7</td>
                        <td>0.7709</td>
                    </tr>                    
                    <tr>
                        <td>LogisticRegression</td>
                        <td>0.7048</td>
                    </tr>
                </table>                
            </li>
        </ul>           
        <br><br><br>
        <ul>
            <li>
                <h2>As the indices were low, some techniques were used to increase them.</h2>
            </li>
            <li>
                One surviving passenger aged 80 was considered an outlier.<br>
                <img src="https://github.com/Rot72/Titanic-kaggle/blob/main/report_age.png">
            </li>
        </ul>
        <h4>Normalization</h4>
        <ul>
            <li>
                One Hot Encoding was used for features Embarked and Sex<br>
                Embarked through the One Hot Encoding became Embarked_C, Embarked_Q, Embarked_S
                Sex had values male and female became Sex_male and Sex_female<br>
            </li>
        </ul>                
        <h4>Transformation - discretization</h4>
        <ul>
            <li>                   
                The cut function is used to create the "Age_Group" column based on the given age groups. Then the get_dummies function is applied on the "Age_Group" column to create the corresponding dummy variables. "Age_Group_" prefixes are added to new column names to indicate age groups.<br>   
                Age was divided into three categories:<br>
                1 - up to 17 years old<br>
                2 - 18 to 64 years old<br>
                3 - over 64 years old<br>
                Each category became a feature Age_Group_1, Age_Group_2 and Age_Group_3
            </li>
        </ul>                    
    </li>
    <li>
        <h4>Confusion Matrix Metrics</h4>
        <ul>
            <li>
                <strong>Accuracy:</strong> It is the proportion of correct predictions to the total number of predictions. It represents the overall prediction accuracy of the model.
            </li>
            <li>
                <strong>Precision:</strong> Also known as Positive Predictive Value, it is the proportion of true positives to the total number of positive predictions (true positives + false positives). It represents the model's ability to correctly identify positive examples.
            </li>
            <li>
                <strong>Recall:</strong> Also known as Sensitivity or True Positive Rate, it is the proportion of true positives to the total number of positive examples (true positives + false negatives). It represents the model's ability to identify all positive examples.
            </li>
            <li>
                <strong>F1-Score:</strong> It is the harmonic mean of Precision and Recall. It is a combined measure that takes into account both the precision and recall of the model. It is useful when there is an imbalance between the classes.
            </li>
        </ul>
    </li>    
    <li>
        <h4>Accuracy of classification</h4>
        <table>
            <thead>
                <tr>
                <th>Model</th>
                <th>True Positive</th>
                <th>False Positive</th>
                <th>False Negative</th>
                <th>True Negative</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>DecisionTreeClassifier</td>
                    <td>93</td>
                    <td>9</td>
                    <td>22</td>
                    <td>55</td>
                </tr>
                <tr>
                    <td>KNeighborsClassifier n_neighbors=3</td>
                    <td>92</td>
                    <td>10</td>
                    <td>14</td>
                    <td>63</td>
                </tr>
                <tr>
                    <td>KNeighborsClassifier n_neighbors=5</td>
                    <td>94</td>
                    <td>8</td>
                    <td>22</td>
                    <td>55</td>
                </tr>
                <tr>
                    <td>KNeighborsClassifier n_neighbors=7</td>
                    <td>91</td>
                    <td>11</td>
                    <td>25</td>
                    <td>52</td>
                </tr>                
                <tr>
                    <td>LogisticRegression</td>
                    <td>96</td>
                    <td>6</td>
                    <td>20</td>
                    <td>57</td>
                </tr>
            </tbody>
        </table>  
    </li>    
    <li>
        <h4>Algorithms</h4>
        <table>
            <tr>
                <th>Model</th>
                <th>Accuracy</th>
                <th>Precision</th>
                <th>Recall</th>
                <th>F1-Score</th>
            </tr>
            <tr>
                <td>DecisionTreeClassifier</td>
                <td>0.8268</td>
                <td>0.8593</td>
                <td>0.7142</td>
                <td>0.7801</td>
            </tr>
            <tr>
                <td>KNeighborsClassifier n_neighbors=3</td>
                <td>0.8659</td>
                <td>0.8630</td>
                <td>0.8181</td>
                <td>0.8400</td>
            </tr>
            <tr>
                <td>KNeighborsClassifier n_neighbors=5</td>
                <td>0.8324</td>
                <td>0.8730</td>
                <td>0.7142</td>
                <td>0.7857</td>
            </tr>
            <tr>
                <td>KNeighborsClassifier n_neighbors=7</td>
                <td>0.7988</td>
                <td>0.8253</td>
                <td>0.6753</td>
                <td>0.7428</td>
            </tr>            
            <tr>
                <td>LogisticRegression</td>
                <td>0.8547</td>
                <td>0.9047</td>
                <td>0.7402</td>
                <td>0.8142</td>
            </tr>
        </table>
    </li>
    <li>
        <h4>Decision</h4>
            Based on the metrics and considerations above, the KNeighborsClassifier model appears to be a solid performer, with a good mix of accuracy, recall, and F1-Score.<br><br>
    <img src="https://github.com/Rot72/Titanic-kaggle/blob/main/chartjs_survived_age_train_test.png"><br><br>
    <img src="https://github.com/Rot72/Titanic-kaggle/blob/main/chartjs_no_survived_age_train_test.png"><br>
    </li>
</ol>
