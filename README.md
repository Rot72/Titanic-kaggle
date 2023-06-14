# Titanic-kaggle
 Machine Learning - Titanic

<!doctype html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <title>Titanics Project</title>
    </head>
    <body>

        <br>
        <br>

        <div class="container">
            <h2 class="text-center">Report</h2>

            <ol class="list-group list-group-numbered">
                <li class="list-group-item d-flex justify-content-between align-items-start">
                    <div class="ms-2 me-auto">
                        <div class="fw-bold">Problem definition:</div>                    
                        The objective is to predict whether or not a passenger survived the Titanic accident based on certain characteristics:Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked.<br><br>
                    </div>
                </li>
                <li class="list-group-item d-flex justify-content-between align-items-start">
                    <div class="ms-2 me-auto">
                    <div class="fw-bold">Collecting and preparing the data:</div>
                    
                        The dataset containing information about Titanic passengers such as age, gender, passenger class, ticket price, etc. has been taken from the website: kaggle.com/competitions/titanic.

                        <a href="https://www.kaggle.com/competitions/titanic" target="_blank">kaggle.com/competitions/titanic</a>.<br>
                        
                        Data preparation, performing tasks such as cleaning, handling missing values and coding categorical variables.

                        <br><br>

                        <a href="report_titanic_before_data_analysis.html" target="_blank">Report before data analysis</a><br><br>

                    <ul>
                        <li class="list-group-item list-group-item-primary">
                            Data Cleaning: titanic_data.csv
                        </li>
<!--
                            Problema: Verifique se há dados duplicados e remova-os, se necessário.
-->                            
                        </li>
                        <li class="list-group-item">  
                            There is no duplicate data.
                        </li>    
                        <li class="list-group-item list-group-item-light"> 
                            Removal of non-numeric values: Name, Ticket and Cabin
                        </li> 
                        <li class="list-group-item list-group-item-light"> 
                            Embarked field had 2 null fields the mode was taken and the value equal to S was found.
                        </li>                         
                        
<!--
                            Problema: Remova colunas que não são relevantes para o problema em questão.
-->
                        <li class="list-group-item list-group-item-light">  
                            <ul>
                                <li>
                                Classification of crew and passengers was analyzed by Survived, Pclass, Sex, Age, SibSp, Parch, Fare, Embarked.
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
<!--
                            Problema: Campos objetos transformam se em numeros
-->
                        <li class="list-group-item list-group-item-light">  
                            <ul>
                                <li>
                                    Sex field through the one hot encoding turned into Sex_female and Sex_male.
                                </li>
                                <li>
                                    Field Embarked through the one hot method became Embarked_C, Embarked_Q, Embarked_S
                                </li>
                                <li>
                                    The cut function is used to create the "Age_Group" column based on the given age groups. Then the get_dummies function is applied on the "Age_Group" column to create the corresponding dummy variables. "Age_Group_" prefixes are added to new column names to indicate age groups.
                                </li>
                            </ul>
                        </li>                        
<!--
                            Problema: Identifique se há outliers nos dados e decida se eles devem ser removidos ou tratados.
-->
                        <li class="list-group-item list-group-item-light"> 
                            One 80 year old survivor in the first class was considered an Outlier.
                        </li>
                        <li class="list-group-item inv">                        
                            Problema: Tratamento de valores ausentes: Verifique se há valores ausentes em cada coluna dos dados. Decida como lidar com os valores ausentes. Você pode optar por remover as linhas que contêm valores ausentes, preencher os valores ausentes com a média/mediana/moda dos dados, ou usar métodos mais avançados, como imputação com base em modelos.
                        </li>

                        <li class="list-group-item list-group-item-light"> 
                            Number of null fields in 'Age': <b>177</b> of 891<br>
                            5+16+2+7+9+85+9+2+25+17 = <b>177</b>
                        </li>
                        <li class="list-group-item list-group-item-light"> 
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



                    <ul>
                        <li class="list-group-item list-group-item-primary">
                            Data Cleaning: titanic_test.csv
                        </li>
<!--
                            Problema: Verifique se há dados duplicados e remova-os, se necessário.
-->                            
                        </li>
                        <li class="list-group-item">  
                            There is no duplicate data.
                        </li>    
                        <li class="list-group-item">  
                        There is an empty value in the Fare column. <br>
                        The average was taken to fill it.<br>
                        Fare: 35.63 £
                        </li>                        
                        <li class="list-group-item list-group-item-light"> 
                            Removal of non-numeric values: Name, Ticket and Cabin
                        </li>          
                        <li class="list-group-item list-group-item-light"> 
                            One hot was used again for Age and Sex fields
                        </li>
                        <li class="list-group-item list-group-item-light"> 
                            Number of null fields in 'Age': <b>86</b> of 418<br>
                            7+4+50+2+1+22 = <b>86</b>
                        </li>

                        <li class="list-group-item list-group-item-light"> 
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

                    <ul>
                        <li class="list-group-item list-group-item-primary">
                            Normalization
                        </li>
                        <li class="list-group-item inv">
                            A normalização refere-se ao processo de ajustar os valores dos dados para uma escala comum, a fim de evitar viés ou influência excessiva de determinadas características. A normalização geralmente envolve redimensionar os valores para um intervalo específico, como 0 a 1 ou -1 a 1. Isso garante que todas as características tenham o mesmo peso ao treinar o modelo e ajuda a melhorar a convergência e o desempenho dos algoritmos de machine learning.
                        </li>
                        <li class="list-group-item list-group-item-light">                   
                            For the "Sex" column, one-hot encoding, also known as dummy encoding, was used. One-hot coding creates a new column for each category of the categorical variable and assigns binary values (0 or 1). 
                        </li>
                    </ul>



                    <ul>
                        <li class="list-group-item list-group-item-primary">
                            Transformation - discretization 
                        </li>
                        <li class="list-group-item inv">
                            A transformação de dados envolve a aplicação de operações matemáticas ou estatísticas nos dados originais para criar novas características ou modificar sua distribuição. Algumas transformações comuns incluem a aplicação de logaritmos, raízes quadradas, exponenciais ou funções trigonométricas aos dados. Essas transformações podem ajudar a tornar os dados mais simétricos, reduzir a heterogeneidade ou melhorar a linearidade das relações entre as variáveis.
                        </li>
                        <li class="list-group-item list-group-item-light">                   
                            A new column called <b>Age Group</b> was created. It was divided into:<br>
                            1 = up to 18 years old<br>
                            2 = 18-64 years old<br>
                            3 = over 64 years old
                        </li>
                    </ul>                    

                </div>

                </li>

                <li class="list-group-item d-flex justify-content-between align-items-start">
                    <div class="ms-2 me-auto">
                        <div class="fw-bold">Accuracy of classification</div><br>

                        <div class="table-responsive">

                            <table class="table text-center">
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
                                        <td>KNeighborsClassifier</td>
                                        <td>92</td>
                                        <td>10</td>
                                        <td>14</td>
                                        <td>63</td>
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
                        </div>
                    </div>            
                </li>


                <li class="list-group-item d-flex justify-content-between align-items-start">
                    <div class="ms-2 me-auto">
                        <div class="fw-bold">Confusion Matrix Metrics</div>
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
                    </div>
                </li>     

                <li class="list-group-item d-flex justify-content-between align-items-start">
                    <div class="ms-2 me-auto">
                        <div class="fw-bold">Algorithms</div><br>

                        <div class="table-responsive">
                            <table class="table table-striped border-secondary">
                                <tr>
                                    <th>Model</th>
                                    <th>Accuracy</th>
                                    <th>Precision</th>
                                    <th>Recall</th>
                                    <th>F1-Score</th>
                                </tr>
                                <tr>
                                    <td>DecisionTreeClassifier</td>
                                    <td>0.8268156424581006</td>
                                    <td>0.859375</td>
                                    <td>0.7142857142857143</td>
                                    <td>0.7801418439716311</td>
                                </tr>
                                <tr>
                                    <td>KNeighborsClassifier</td>
                                    <td>0.8659217877094972</td>
                                    <td>0.863013698630137</td>
                                    <td>0.8181818181818182</td>
                                    <td>0.8400000000000001</td>
                                </tr>
                                <tr>
                                    <td>LogisticRegression</td>
                                    <td>0.8547486033519553</td>
                                    <td>0.9047619047619048</td>
                                    <td>0.7402597402597403</td>
                                    <td>0.8142857142857143</td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </li>

<!--
    Accuracy (Acurácia): É a proporção de predições corretas em relação ao total de predições. Representa a taxa geral de acerto do modelo.

    Precision (Precisão): Também conhecida como Valor Preditivo Positivo, é a proporção de verdadeiros positivos em relação ao total de predições positivas (verdadeiros positivos + falsos positivos). Representa a habilidade do modelo em identificar corretamente os exemplos positivos.

    Recall (Revocação): Também conhecido como Sensibilidade ou Taxa de Verdadeiros Positivos, é a proporção de verdadeiros positivos em relação ao total de exemplos positivos (verdadeiros positivos + falsos negativos). Representa a habilidade do modelo em identificar todos os exemplos positivos.

    F1-Score: É a média harmônica entre Precision e Recall. É uma medida combinada que leva em consideração tanto a precisão quanto a revocação do modelo. É útil quando o balanceamento entre as classes é desigual.
-->


                <li class="list-group-item d-flex justify-content-between align-items-start">
                    <div class="ms-2 me-auto">
                        <div class="fw-bold">Decision</div>
                            Based on the metrics and considerations above, the KNeighborsClassifier model appears to be a solid performer, with a good mix of accuracy, recall, and F1-Score.
                    </div>
                </li>
            </ol>
            
            <br>
            <br>
        </div>
    </body>
</html>
