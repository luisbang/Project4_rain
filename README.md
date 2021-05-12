# Projeto 4 - Will it rain tomorrow?

## ● Objetivo

### Cliente : O Vendedor de guarda chuva / capa de chuva na Australia
Oferecer uma previsão de se vai chover amanhã ou não para o cliente decidir se vai levar os produtos de chuva ou não.

## ● Procedimento

- Tratamento de dados - Com os dados de históricos de chuva e vento na Austrália, foi feito seguintes passos :
  
  1. Os datas foram classificados como estação do ano da Austrália (Primavera(3), Verão(4), Outono(1), Inverno(2))
  2. As coluns como amountOfRain, modelo_vigente, rainfall foram eliminadas da tabela para evitar o vazamento de dados

- Preparando o modelo de Machine Learning:
  
  1. Primeiramente o modelo escolhido foi LGBMClassifier.
  2. Escolha de test_size para separar os dados de treino e test: Atravé de curava de aprendizagem foi definido 25% para test_size(3500 /142193)
  
  ![image](https://user-images.githubusercontent.com/79090589/118017165-abf7aa80-b32c-11eb-8444-b1facb0e8664.png)
 
  3. Utilizando Feature selection foi escolhido as colunas que influnência no modelo
 
 ![image](https://user-images.githubusercontent.com/79090589/118017754-5bcd1800-b32d-11eb-8fd7-294911792e29.png)

(mintemp, maxtemp, evaporation, sunshine, humidity9am, humidity3pm, pressure9am, pressure3pm, cloud3pm, temp9am, temp3pm, raintoday, temp, humidity, wind_gustspeed, wind_speed9am, wind_speed3pm, season)

  4. Para a escolha do melhor modelo para este dado, foi utilizado Pycaret

![image](https://user-images.githubusercontent.com/79090589/118027897-d2234780-b338-11eb-8614-2376da5c764c.png)
 
 como a imagem acima, melhor modelo definido pelo Pyacaret foi RandomForest
 Após a tunagem do modelo, obtive seguinte resultado
 
 ![image](https://user-images.githubusercontent.com/79090589/118032262-d7cf5c00-b33d-11eb-958e-0b8e48c1315f.png)
 
 ## Resultado

Utilizando o modelo final para os dados reais, para isso obtive os dados de 1/5 a 11/5 (fonte : http://www.bom.gov.au/climate/dwo/IDCJDW3050.latest.shtml)
e aplicando o modelo, obtive seguinte resultado.

![image](https://user-images.githubusercontent.com/79090589/118033873-b1aabb80-b33f-11eb-80db-f9b733528fdd.png)

