# Generalized-Linear-Models_Classes



## title: "Modelos Lineares Generalizados"
## authors: "Class of 2017.1"
## date: "10 de Novembro"
## output: html_document


<br/>
<br/>
<p align="right">
   <br/>
 Turma_2017.1<br/>
  
   <br/>  
  Universidade Estadual da Paraíba<br/>
  
  <br/>
  http://departamentos.uepb.edu.br/estatistica/corpo-docente/ <br/>  
</p> 

<br/>
<br/>

## *<span style="color: black">Centro de Ciência e Tecnologia</span>*

## *<span style="color: black">Departamento de Estatística</span>*

## *<span style="color: black">UEPB - CCT - DE</span>*
  

<br/>
<br/>  

![Use R!](http://developer.r-project.org/Logo/Rlogo-5.png) 

Introdução básica de R pode ser encontrada [Aqui](https://cran.r-project.org/doc/contrib/Landeiro-Introducao.pdf)

<br/>
<br/> 

## R Markdown

Sobre R Markdown, pode ser consultada [Aqui](http://www.leg.ufpr.br/~fernandomayer/useR/Rmarkdown-rautu.html)

<br/>
<br/>

Apostilas correspondentes à disciplina "<span style="color: blue">**Modelos Lineares Generalizados**</span>":

[Gilberto de Paula](https://www.ime.usp.br/~giapaula/texto_2013.pdf) e [Gauss e Clarice](http://www.lce.esalq.usp.br/arquivos/aulas/2010/LCE5868/livro.pdf).

<br/>
<br/>


# *<span style="color: dark blue">Uma breve revisão sobre modelos de regressão</span>*

<br/>
<br/>

## **Modelos de Regressão**

<br/>

O objetivo da análise de regressão é fornecer uma ferramenta estatística que permita modelar e investigar a relação entre duas ou mais variáveis.  


**_Regressão Linear Simples_** (**RLM**)

1º O modelo:  

* Modelo inicial: ```Y=f(x)```

2º A formulação estatística:

* COMPONENTE SISTEMÁTICA + COMPONENTE ALEATÓRIA  

 A componente sistemática é expressa por uma função especificada pelo analista, enquanto que, a componente aleatória é representada por uma distribuição de probabilidade. Ou seja,

<p align="center">
 <img src="https://latex.codecogs.com/gif.latex?Y%3Df%28x%29&plus;%5Cepsilon" />
 </p>

A relação entre a variável resposta ```Y```e a variável explicativa ```X``` é postulada como um modelo linear:  

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?Y%3D%5Cbeta_0&plus;%5Cbeta_1X&plus;%5Cepsilon%20%5Cqquad%5Cmbox%7B%7D%5Cqquad%20%5Cquad%5Cmbox%7B%281%29%7D%5Cquad" />
 </p>
<br/>

_**O que é "linear"**_?
<br/>

 __Obs__:O adjetivo "_linear_" tem sentido duplo. Ele pode descrever, de fato, que a relação entre ```Y``` e ```X``` é linear (reta). Mas, geralmente, a palavra linear refere-se ao modo como os parâmetros entram no modelo. Ou seja, a linearidade é nos parâmetros. Por exemplo,

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?Y%3D%5Cbeta_0&plus;%5Cbeta_1X%5E2&plus;%5Cepsilon" />
   </p>

é um modelo linear, apesar da relação entre ```Y``` e ```X``` ser quadrática. 

Porém, temos também um exemplo em que não há a presença da linearidade nos parâmetros:

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?Y%3D%5Cbeta_0X%5E%7B%5Cbeta_1%7D%5Cepsilon" />
   </p>

  Logo, trata-se de um modelo não linear.

<br/>

#### **Modelo Amostral**

<br/>

 Suponha que temos ```n``` observações de ```X``` e ```Y``` <img src="https://latex.codecogs.com/gif.latex?%5B%28x_1%2Cy_1%29%2C%20%28x_2%2Cy_2%29%2C%20...%2C%20%28x_n%2Cy_n%29%5D" />. Então, por (1), podemos escrever:
<p align="center">
<img src="https://latex.codecogs.com/gif.latex?y_i%3D%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon_i%2C%20%5Cquad%5Cmbox%7Bpara%20i%3D%201%2C%20...%2C%20n.%7D%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%282%29%7D%5Cquad" />
   </p>

 Ainda, temos que:
 
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cepsilon_i%5Cstackrel%7Biid%7D%5Csim%20N%280%2C%5Csigma%5E2%29%20%5Cquad%5Cmbox%7Be%7D%5Cquad%20E%5BY%7CX%3Dx%5D%3D%5Cbeta_0&plus;%5Cbeta_1x" />
   </p>

<br/>

Logo, a esperança e variância serão, respectivamente:

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?E%5By_i%5D%3DE%5B%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon%5D%3D%20%5Cbeta_0&plus;%5Cbeta_1x_i" />
   </p>
e

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?Var%5By_i%5D%3DVar%5B%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon%5D%3DVar%5B%5Cepsilon%5D%3D%5Csigma%5E2" />
   </p>

Os erros correspondentes às observações distintas são não correlacionadas, ou seja, <img src="https://latex.codecogs.com/gif.latex?cov%28%5Cepsilon_i%2C%20%5Cepsilon_j%29%3D0%24%20%24%5Cforall_i%5Cneq%7Bj%7D" />, ou equivalentemente <img src="https://latex.codecogs.com/gif.latex?E%5B%5Cepsilon_i%20%5Cepsilon_j%5D%3D0%24%2C%24%5Cforall_i%5Cneq%7Bj%7D" />.

Se assumirmos normalidade para os erros, isto é, <img src="https://latex.codecogs.com/gif.latex?%5Cepsilon_i%5Csim%20N%280%2C%5Csigma%5E2%29" />.

<br/>

* **_OBS¹_**: Vejamos a _distribuição Normal_


<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?f_Y%28y%29%3D%5Cfrac%7B1%7D%7B%5Csqrt%7B2%5Cpi%7D%5Csigma%7D%7B%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E2%7D%7B%28y-%5Cmu%29%5E2%7D%5Cright%5C%7D%7D_%7BI_%7B%28-%5Cinfty%3B%5Cinfty%29%5Ey%7D%7D" />
   </p>
e

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cmathbf%7B%5CTheta%3D%5C%7B%28%5Cmu%2C%5Csigma%5E2%29%3A-%5Cinfty%5Cle%5Cmu%5Cle%5Cinfty%20%3B%20%5Csigma%5E2%3E0%5C%7D%7D" />
   </p>

 Ou seja,

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?Y%5Csim%20N%28%5Cbeta_0&plus;%5Cbeta_1x_i%3B%5Csigma%5E2%29" />
   </p>
   
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?f_Y%28y%29%3D%5Cfrac%7B1%7D%7B%5Csqrt%7B2%5Cpi%7D%5Csigma%7D%7B%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E2%7D%7B%5By-%28%5Cbeta_0&plus;%5Cbeta_1x_i%29%5D%5E2%7D%5Cright%5C%7D%7D_%7BI_%7B%28-%5Cinfty%3B%5Cinfty%29%5Ey%7D%7D%20%5Cquad%5Cmbox%7B%7D%5Cquad" />

<br/>

* **_OBS²_**: É importante verificar se o número de observações disponíveis é maior do que o número de parâmetros da equação de regressão.

<br/>

#### **Estimação dos parâmetros**

<br/>


* _OBJETIVO_: Obter os estimadores para os parâmetros desconhecidos;
* _MÉTODO_: Mínimos Quadrados Ordinários (_**MQO**_);
* _IDEIA_: Escolher a reta que minimiza a soma de quadrados dos erros, ou seja, que minimiza <img src="https://latex.codecogs.com/gif.latex?%5Csum%5Climits_%7Bi%3D1%7D%5En%5Cepsilon_i%5E2" />;
* _PROCEDIMENTO_: Dado ```n``` observações sobre ```X``` e ```Y``` desejamos minimizar:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?y_i%3D%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon_i%5Crightarrow%20%5Cepsilon_i%3Dy_i-%28%5Cbeta_0&plus;%5Cbeta_1x_i%29" />
</p>
<br/>
então,

<p align="center">
<img src="https://latex.codecogs.com/gif.latex?S%28%5Cbeta_0%2C%5Cbeta_1%29%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Cepsilon_i%5E2%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5By_i-%28%5Cbeta_0&plus;%5Cbeta_1x_i%29%5D%5E2" />
   </p>

<br/>

**OBSERVAÇÕES:**

<br/>

1. Note que na regressão precisamos fazer suposições sobre a distribuição de <img src="https://latex.codecogs.com/gif.latex?%5Cepsilon_i" /> para obtermos <img src="https://latex.codecogs.com/gif.latex?%5Chat%5Cbeta_0" /> e <img src="https://latex.codecogs.com/gif.latex?%5Chat%5Cbeta_1" />.

2. Se a reta de regressão se ajusta bem aos dados, então podemos utilizá-la para fazer __predições__, desde que não ultrapassem os limites dos valores disponíveis.
<br/>

Se assumirmos normalidade e admitirmos que os elementos da amostra são independentes, a função de verossimilhança para <img src="https://latex.codecogs.com/gif.latex?y_1%2C%20...%2C%20y_n" /> é
<br/>

<p align="center">
<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20L%28%5Cbeta_0%2C%5Cbeta_1%2C%5Csigma%5E2%3By%29%26%3D%5Cprod%5Climits_%7Bi%3D1%7D%5Enf_Y%28y_1%2C...%2Cy_n%3B%5Cbeta_0%2C%5Cbeta_1%2C%5Csigma%5E2%29%5C%5C%20%26%3D%5Cprod%5Climits_%7Bi%3D1%7D%5En%20%5Cfrac%7B1%7D%7B%5Csqrt%7B2%5Cpi%7D%5Csigma%7D%7B%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E2%7D%7B%28y_i-%5Cbeta_0-%5Cbeta_1x_i%29%5E2%7D%5Cright%5C%7D%7D%5C%5C%20%26%3D%5Cfrac%7B1%7D%7B%5Csigma%5En%282%5Cpi%29%5E%7Bn/2%7D%7D%7B%5Cexp%5Cleft%5C%7B%7B-%5Cfrac%7B1%7D%20%7B2%5Csigma%5E2%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%28y_i-%5Cbeta_0-%5Cbeta_1x_i%29%5E2%7D%5Cright%5C%7D%7D%20%5Cend%7Balign*%7D" />
</p>
<br/>

 Se maximizarmos a função acima com relação a <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_0" />, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_1" /> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csigma%5E2" /> obtemos exatamente os mesmos estimadores para <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_0">, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_1" /> fornecidos pelo __Método dos Mínimos Quadrados Ordinários__.


<br/>

#### **_Propriedades Amostrais_** 

* O que podemos dizer sobre <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_0" /> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_1" /> ?

<br/>

1. São funções lineares de <img src="https://latex.codecogs.com/gif.latex?y_i" />.

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_0%3D%5Cbar%7By%7D-%5Chat%5Cbeta_1%5Cbar%7Bx%7D%3D%5Cbar%7By%7D-%5Csum%5Climits_%7Bi%3D1%7D%5Eny_ia_i%5Cbar%7Bx%7D%3D%5Csum%5Climits_%7Bi%3D1%7D%5Eny_i%5Cleft%28%5Cfrac%7B1%7D%7Bn%7D%7B-a_i%5Cbar%7Bx%7D%7D%5Cright%29%3D%5Csum%5Climits_%7Bi%3D1%7D%5Eny_ib_i" />
   </p>
<br/>

 E, ainda temos que:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_0%3D%5Cbar%7By%7D-%5Chat%5Cbeta_1%5Cbar%7Bx%7D%3D%5Cbar%7By%7D-%5Csum%5Climits_%7Bi%3D1%7D%5Eny_ia_i%5Cbar%7Bx%7D%3D%5Csum%5Climits_%7Bi%3D1%7D%5Eny_i%5Cleft%28%5Cfrac%7B1%7D%7Bn%7D%7B-a_i%5Cbar%7Bx%7D%7D%5Cright%29%3D%5Csum%5Climits_%7Bi%3D1%7D%5Eny_ib_i" />
   </p>
<br/>
 Logo,
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_0%3D%5Csum%5Climits_%7Bi%3D1%7D%5Eny_ib_i" />
   </p>
<br/>

 Podemos mostrar que se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20y_i" /> tem distribuição Normal, então <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_0" /> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_1" /> também possuem distribuição _NORMAL_.

<br/>

2. <img src="https://latex.codecogs.com/gif.latex?%5Chat%5Cbeta_0" /> e <img src="https://latex.codecogs.com/gif.latex?%5Chat%5Cbeta_1" /> são estimadores não-viesados de <img src="https://latex.codecogs.com/gif.latex?%5Cbeta_0"> e <img src="https://latex.codecogs.com/gif.latex?%5Cbeta_1" />, respectivamente.

<br/>

<p align="center>
          <img src= "https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20E%5B%5Chat%5Cbeta_1%5D%26%3DE%5Cleft%5B%5Csum_%7Bi%3D1%7D%5E%7Bn%7Dy_ia_i%5Cright%5D%5Cnonumber%5C%5C%20%26%3D%5Csum_%7Bi%3D1%7D%5E%7Bn%7DE%5By_ia_i%5D%5Cnonumber%5C%5C%20%26%3D%5Csum_%7Bi%3D1%7D%5E%7Bn%7Da_iE%5By_i%5D%5Cnonumber%5C%5C%20%26%3D%5Csum_%7Bi%3D1%7D%5E%7Bn%7Da_i%28%5Cbeta_0&plus;%5Cbeta_1x_i%29%5Cnonumber%5C%5C%20%26%3D%5Cbeta_0%5Csum_%7Bi%3D1%7D%5E%7Bn%7Da_i&plus;%5Cbeta_1%5Csum_%7Bi%3D1%7D%5E%7Bn%7Da_ix_i%20%5Cend%7Balign*%7D" />
                      <p/>

<br/>

* Quem é <img src="https://latex.codecogs.com/gif.latex?%5Ctiny%20%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_i" /> e <img src="https://latex.codecogs.com/gif.latex?%5Ctiny%20%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_ix_i" /> ?

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cmathbf*%5Csum_%7Bi%3D1%7D%5E%7Bn%7Da_i%3D%5Cfrac%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%20%3D%5Cfrac%7B1%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%5Ccdot%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%3D0" />
   </p>
E,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cmathbf*%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_ix_i%3D%5Cfrac%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Dx_i%28x_i-%5Cbar%7Bx%7D%29%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%3D%5Cfrac%7B1%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%5Ccdot%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%3D1" />
   </p>
   
<br/>

 Portanto,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%5B%5Chat%5Cbeta_1%5D%3D%5Cbeta_0%5Ccdot0&plus;%5Cbeta_1%5Ccdot1%3D%5Cbeta_1%5CRightarrow%20E%5B%5Chat%5Cbeta_1%5D%3D%5Cbeta_1" />
  </p>

<br/>

3. <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20Var%5B%5Chat%5Cbeta_0%5D%3D%5Csigma%5E2%20%5Cleft%28%5Cfrac%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Dx_i%5E2%7D%7Bn%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i%5Cbar%7Bx%7D%29%5E2%7D%5Cright%29" />
   </p>

<br/>

<p align="center">
<img src="https://latex.codecogs.com/gif.latex?%5Csmall%20Var%5B%5Chat%5Cbeta_1%5D%3D%5Cfrac%7B%5Csigma%5E2%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%5Cquad%5Cmbox%7Be%7D%5Cquad%5Cquad%20COV%5B%5Chat%5Cbeta_0%2C%5Chat%5Cbeta_1%5D%3D-%5Cfrac%7B%5Csigma%5E2%5Cbar%7Bx%7D%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D" />
   </p>
<br/>

Mostrando se, de fato, a variância de <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Chat%5Cbeta_1%3D%5Cfrac%7B%5Csigma%5E2%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D" />. Então,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20Var%5B%5Chat%5Cbeta_1%5D%26%3DVar%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_iy_i%5Cright%5D%5Cnonumber%5C%5C%20%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7DVar%5Ba_iy_i%5D%20%3D%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_i%5E2Var%5By_i%5D%20%3D%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_i%5E2%5Csigma%5E2%20%3D%5Csigma%5E2%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_i%5E2%5Cnonumber%5C%5C%20%26%3D%5Csigma%5E2%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%5Cleft%5B%5Cfrac%7B%28x_i-%5Cbar%7Bx%7D%29%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%5Cright%5D%5E2%20%3D%5Csigma%5E2%5Cfrac%7B1%7D%7B%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2%5Cright%5D%5E2%7D%5Ccdot%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2%5Cnonumber%5C%5C%20%26%3D%5Cfrac%7B%5Csigma%5E2%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%20%5Cend%7Balign*%7D" />
   </p>

<br/>

 Agora, verificaremos, se <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20COV%28%5Chat%5Cbeta_0%2C%5Chat%5Cbeta_1%29%3D-%5Cfrac%7B%5Csigma%5E2%5Cbar%7Bx%7D%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D"/> :

<br/>

 Então,

<br/>

<p align="center">
<img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20COV%28%5Chat%5Cbeta_0%2C%5Chat%5Cbeta_1%29%26%3DCOV%28%5Cbar%7By%7D-%5Chat%5Cbeta_%7B1%7D%5Cbar%7Bx%7D%2C%5Chat%5Cbeta_1%29%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-COV%28%5Chat%5Cbeta_1%5Cbar%7Bx%7D%2C%5Chat%5Cbeta_1%29%5Cnonumber%5C%5C%20%26%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-%5Cbar%7Bx%7DCOV%28%5Chat%5Cbeta_1%2C%5Chat%5Cbeta_1%29%5Cnonumber%5C%5C%20%26%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-%5Cbar%7Bx%7DVar%28%5Chat%5Cbeta_1%29%5Cnonumber%5C%5C%20%26%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-%7B%5Cfrac%7B%5Cbar%7Bx%7D%5Csigma%5E2%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%7D%20%5Cend%7Balign*%7D" />
   </p>

<br/>

* **_Obs_**: A _Esperança_ e a _Variância_ de <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Chat%5Cbeta_0" /> foram dadas como exercício para os discentes.

<br/>

 Agora, temos que provar que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20COV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29%3D0" /> :
 
 <br/>

<p align="center">
   <imgsrc="https://latex.codecogs.com/gif.latex%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cbar%7By%7D%26%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5Eny_i%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%28%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon_i%29%5Cnonumber%5C%5C%20%26%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%28%5Cbeta_0&plus;%5Cbeta_1x_i%29&plus;%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Cepsilon_i%5Cnonumber%5C%5C%20%26%3D%5Cfrac%7Bn%5Cbeta_0%7D%7Bn%7D&plus;%5Cbeta_1%5Cfrac%7B%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%7D%7Bn%7D&plus;%5Cbar%7B%5Cepsilon%7D%3D%5Cbeta_0&plus;%5Cbeta_1%5Cbar%7Bx%7D&plus;%5Cbar%7B%5Cepsilon%7D%20%5Cend%7Balign*%7D" />
   </p>
   
<br/>

 Sabendo que,

<br/>

<p align="center">
      <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%5B%5Cbar%7By%7D%5D%3DE%5B%5Cbeta_0&plus;%5Cbeta_1%5Cbar%7Bx%7D&plus;%5Cbar%7B%5Cepsilon%7D%5D%3DE%5B%5Cbeta_0%5D&plus;E%5B%5Cbeta_1%5Cbar%7Bx%7D%5D&plus;E%5B%5Cbar%7B%5Cepsilon%7D%5D%3D%5Cbeta_0&plus;%5Cbeta_1%5Cbar%7Bx%7D" />
   </p>
   
   </br>

 Daí,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbar%7By%7D%3DE%5B%5Cbar%7By%7D%5D&plus;%5Cbar%7B%5Cepsilon%7D%5CRightarrow%20%5Cbar%7B%5Cepsilon%7D%3D%5Cbar%7By%7D-E%5B%5Cbar%7By%7D%5D" />
   </p>
   
<br/>
 
Por outro lado,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20%5Chat%5Cbeta_1%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5Ena_iy_i%3D%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%28%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon_i%29%5Cnonumber%5C%5C%20%26%3D%5Cbeta_0%5Csum%5Climits_%7Bi%3D0%7D%5Ena_i&plus;%5Cbeta_1%5Csum%5Climits_%7Bi%3D1%7D%5Ena_ix_i&plus;%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%5Cepsilon_i%5Cnonumber%5C%5C%20%5CRightarrow%5Chat%5Cbeta_1%26%3D%5Cbeta_1&plus;%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%5Cepsilon_i%20%5Cend%7Balign*%7D" />
</p>

<br/>

 Logo,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Chat%5Cbeta_1-%5Cbeta_1%3D%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%5Cepsilon_i%5CRightarrow%20%5Chat%5Cbeta_1-E%5B%5Chat%5Cbeta_1%5D%3D%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%5Cepsilon_i%2C" />
   </p>

<br/>

Segue que,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20Cov%5By%2C%5Chat%5Cbeta_1%5D%26%3DE%5B%28%5Cbar%7By%7D-E%5B%5Cbar%7By%7D%5D%29%28%5Chat%5Cbeta_1-E%5B%5Chat%5Cbeta_1%5D%29%5D%3DE%5Cleft%5B%5Cbar%7B%5Cepsilon%7D%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%5Cepsilon_i%5Cright%5D%5Cnonumber%5C%5C%20%26%3DE%5Cleft%5B%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Cepsilon_i%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%5Cepsilon_i%5Cright%5D%3D%5Cfrac%7B1%7D%7Bn%7DE%5B%28%5Cepsilon_1&plus;%5Cepsilon_2&plus;...&plus;%5Cepsilon_n%29%28a_1%5Cepsilon_1&plus;a_2%5Cepsilon_2&plus;...&plus;a_n%5Cepsilon_n%29%5D%5C%5C%20%26%3D%5Cfrac%7B1%7D%7Bn%7DE%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Da_i%5Cepsilon_i%5E2&plus;%5Csum%5Climits_%7Bi%5Cneq%7Bj%7D%7D%5Ena_i%5Cepsilon_i%5Cepsilon_j%5Cright%5D%5Cnonumber%5C%5C%20%26%3D%5Cfrac%7B1%7D%7Bn%7D%5Cleft%5BE%5Cleft%28%5Csum%5Climits_%7Bi%3D1%7D%5Ena_i%5Cepsilon_i%5E2%5Cright%29&plus;E%5Cleft%28%5Csum%5Climits_%7Bi%5Cneq%7Bj%7D%7D%5Ena_i%5Cepsilon_i%5Cepsilon_j%5Cright%29%5Cright%5D%5C%5C%20%26%3D%5Cfrac%7B1%7D%7Bn%7D%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5EnE%5Cleft%28a_i%5Cepsilon_i%5E2%5Cright%29&plus;%5Csum%5Climits_%7Bi%5Cneq%7Bj%7D%7D%5EnE%5Cleft%28a_i%5Cepsilon_i%5Cepsilon_j%5Cright%29%5Cright%5D%5C%5C%20%26%3D%5Cfrac%7B1%7D%7Bn%7D%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5Ena_iE%5Cleft%28%5Cepsilon_i%5E2%5Cright%29&plus;%5Csum%5Climits_%7Bi%5Cneq%7Bj%7D%7D%5Ena_iE%5Cleft%28%5Cepsilon_i%5Cepsilon_j%5Cright%29%5Cright%5D%20%5Cend%7Balign*%7D" />
   </p>
   
<br/>

 Como,
 
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20Var%5B%5Cepsilon_i%5D%26%3DE%5B%5Cepsilon_i%5D-%5BE%28%5Cepsilon_i%29%5D%5E2%20%5CRightarrow%5Csigma%5E2%26%3DE%5B%5Cepsilon_i%5E2%5D%20%5Cend%7Balign*%7D" />
   </p>

<br/>

 Temos que,
 
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20COV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum_%7Bi%3D1%7D%5E%7Bn%7Da_i%5Csigma%5E2%3D%5Cfrac%7B%5Csigma%5E2%7D%7Bn%7D%5Csum_%7Bi%3D1%7D%5E%7Bn%7Da_i" />
   </p>

<br/>

 Deste modo,
 
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20COV%28%5Chat%5Cbeta_0%2C%5Chat%5Cbeta_1%29%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-%5Cfrac%7B%5Cbar%7Bx%7D%5Csigma%5E2%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%3D-%5Cfrac%7B%5Cbar%7Bx%7D%5Csigma%5E2%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D" />
   </p>

<br/>

**Observações:**

1. Quanto maior o <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csigma%5E2" />, maior a variância dos estimadores.

2. Quanto maior a variabilidade amostral de x, menor a variabilidade dos estimadores.

<br/>

#### Estimação de <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csigma%5E2" />
<br/>

 Como estimar o parâmetro de dispersão <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csigma%5E2"/> ?

 Dado que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%5B%5Cepsilon_i%5D%3D0" />, temos que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%28%5Cepsilon_i%5E2%29%3D%5Csigma%5E2" />. Assim,
 
 <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%5Cepsilon_i%5E2%5Cright%5D%3D%5Csum_%7Bi%3D1%7D%5E%7Bn%7DE%28%5Cepsilon_i%5E2%29%3D%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%5Csigma%5E2%3Dn%5Csigma%5E2" />
   </p>
 
<br/>
e, portanto,
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%5Cleft%5B%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%5Cfrac%7B%5Cepsilon_i%5E2%7D%7Bn%7D%5Cright%5D%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum_%7Bi%3D1%7D%5E%7Bn%7DE%5B%5Cepsilon_i%5E2%5D%3D%5Cfrac%7B1%7D%7Bn%7Dn%5Csigma%5E2%3D%5Csigma%5E2" />
   </p>
   
   </br>

 Deste modo, <img src="https://latex.codecogs.com/gif.latex?%5Ctiny%20%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%5Cepsilon_i%5E2" /> será um estimador não viesado para <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csigma%5E2" />.
<br/>
*PROBLEMA:* Os erros são desconhecidos, portanto, não podemos usá-lo para estimar <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csigma%5E2" />.
<br/>

* Idéia: Usar os estimadores dos erros;
* Erro: <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cepsilon%3Dy_i-%5Cbeta_0-%5Cbeta_1x_i" />;
* Resíduo: <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Chat%5Cepsilon_i%3Dy_i-%5Chat%5Cbeta_0-%5Chat%5Cbeta_1x_i" />.

 Assim, estimaremos a variância <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csigma%5E2" />, usando
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%5Chat%5Cepsilon_i%5E2" />
   </p>
 No entanto, este estimador é viesado.
<br/>

Podemos mostrar que um estimador não viesado para <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csigma%5E2" /> será dado por:
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Chat%5Csigma%5E2%3D%5Cfrac%7B1%7D%7Bn-1%7D%5Csum_%7Bi%3D1%7D%5E%7Bn%7D%5Chat%5Cepsilon_i%5E2" />
   </p>

<br/>

#### Teorema de Gauss-Markov
<br/>

 Sob condições do modelo, temos que os estimadores de _MQO_ são não viesados e de variância mínima.

<br/>

**Demonstração**:
<br/>

 Consideremos um estimador linear qualquer de <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbeta_1" />. Digamos:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20B%3D%5Csum%5Climits_%7Bi%3D1%7D%5Enc_iy_i%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%28%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon_i%29%5C%5C%20%26%3D%5Cbeta_0%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i&plus;%5Cbeta_1%5Csum%5Climits_%7Bi%3D1%7D%5Enc_ix_i&plus;%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5Cepsilon_i%20%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%281%29%7D%5Cquad%20%5Cend%7Balign*%7D" />
<br/>
   
 Lembrando que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%5B%5Cepsilon_i%5D%3D0%20%5Cquad%20%5Cforall_i" />, temos que
<br/>

   <p align="center">
      <img src=
"https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24E%5BB%5D%3D%5Cbeta_0%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i&plus;%5Cbeta_1%20%5Csum%5Climits_%7Bi%3D1%7D%5Enc_ix_i" />
      </p>
<br/>

**OBS**: Considerar <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20x_i"/> fixo, ou seja, <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20x_i"/> não é uma V.A. .
<br/>

 Para que ```B``` seja um estimador  não viesado para <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbeta_1" />, devemos observar que,
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%3D0%20%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%282%29%7D%5Cquad" />
   </p>
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%20%5Csum%5Climits_%7Bi%3D1%7D%5Enc_ix_i%3D1%20%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%283%29%7D%5Cquad" />
   </p>
<br/>

Substituindo ```(2)``` e ```(3)``` em ```(1)```:

<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%20B%3D%5Cbeta_0%5Ccdot0&plus;%5Cbeta_1%5Ccdot%7B1%7D&plus;%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5Cepsilon_i%5CRightarrow%20B%3D%5Cbeta_1&plus;%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5Cepsilon_i%5CRightarrow%20B-%5Cbeta_1%3D%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5Cepsilon_i" />
  </p>

<br/>

 A variância de ```B``` é dada por:
<br/>

<p align="center">
<img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20Var%5BB%5D%26%3DE%5B%28B-E%28B%29%5E2%29%5D%5C%5C%20%26%3DE%5B%28B-%5Cbeta_1%29%5E2%5D%3DE%5Cleft%5B%5Cleft%28%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5Cepsilon_i%5Cright%29%5E2%5Cright%5D%5C%5C%20%26%3DE%5B%28c_1%5Cepsilon_1&plus;...&plus;c_n%5Cepsilon_n%29%28c_1%5Cepsilon_1&plus;...&plus;c_n%5Cepsilon_n%29%5D%5C%5C%20%26%3DE%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5E2%5Cepsilon_i%5E2&plus;%5Csum%5Climits_%7Bi%5Cneq%7Bj%7D%7D%5Enc_ic_j%5Cepsilon_i%5Cepsilon_j%5Cright%5D%3DE%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5E2%5Cepsilon_i%5E2%5Cright%5D&plus;E%5Cleft%5B%5Csum%5Climits_%7B%5Cneq%7Bj%7D%7D%5Enc_ic_j%5Cepsilon_i%5Cepsilon_j%5Cright%5D%5C%5C%20%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5E2E%5B%5Cepsilon_i%5E2%5D&plus;%5Csum%5Climits_%7Bi%3D1%7D%5Enc_ic_jE%5B%5Cepsilon_i%5Cepsilon_j%5D%3D%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5Csigma%5E2%5C%5C%20%26%3D%5Csigma%5E2%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i%5E2%20%5Cend%7Balign*%7D" />
   </p>

<br/>

Agora, temos que determinar os valores de <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20c_i" />que minimizam a variância de ```B``` sujeita às condições ```(2)``` e ```(3)```.
<br/>
Aplicando o método dos multiplicadores de _Lagrange_, definimos a seguinte função:
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24F%3D%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i-%5Clambda_1%5Cleft%28%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i-0%5Cright%29-%5Clambda_2%5Cleft%28%5Csum%5Climits_%7Bi%3D1%7Dc_ix_i-1%5Cright%29" />
   </p>
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5Cfrac%7B%5Cpartial%7BF%7D%7D%7B%5Cpartial%7Bc_i%7D%7D%3D2c_i-%5Clambda_1-%5Clambda_2x_i%3D0%20%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%284%29%7D%5Cquad"/>
   </p>
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5CRightarrow%202%5Csum%5Climits_%7Bi%3D1%7D%5Enc_i-n%5Clambda_1-%5Clambda_2%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%3D0%20%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%285%29%7D%5Cquad"/>
   </p>
<br/>

 Substituindo a condição ```(2)``` em ```(5)```
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20-n%5Clambda_1-%5Clambda_2%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%26%3D0%20%5CRightarrow-n%5Clambda_1%3D%5Clambda_2%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%5C%5C%20%5Clambda_1%26%3D%5Clambda_2%5Cfrac%7B%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%7D%7Bn%7D%5C%5C%20%5Clambda_1%26%3D-%5Clambda_2%5Cbar%7Bx%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

 Substituindo <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Clambda_1" /> em ```(4)```, temos:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%202c_i-%28-%5Clambda_2%5Cbar%7Bx%7D%29-%5Clambda_2x_i%26%3D0%202c_i&plus;%5Clambda_2%5Cbar%7Bx%7D-%5Clambda_2x_i%3D0%5C%5C%202c_i%26%3D%5Clambda_2x_i-%5Clambda_2%5Cbar%7Bx%7D%5C%5C%20c_i%26%3D%5Cfrac%7B%5Clambda_2%28x_i-%5Cbar%7Bx%7D%29%7D%7B2%7D%2C%20%5Cforall_i%20%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%286%29%7D%5Cquad%20%5Cend%7Balign*%7D" />
   </p>

<br/>

 Multiplicando ambos os lados de ```(6)``` por <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20x_i" /> e somando as ```n``` igualdades, obtemos:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5Csum%5Climits_%7Bi%3D1%7D%5Enc_ix_i%3D%5Cfrac%7B%5Clambda_2%7D%7B2%7D%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%28x_i-%5Cbar%7Bx%7D%29" />
   </p>
<br/>

 Aplicando a condição ```(3)```:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%241%3D%5Cfrac%7B%5Clambda_2%7D%7B2%7D%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%28x_i-%5Cbar%7Bx%7D%29%5CRightarrow%5Cfrac%7B%5Clambda_2%7D%7B2%7D%3D%5Cfrac%7B1%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%28x_i-%5Cbar%7Bx%7D%29%7D%20%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%287%29%7D%5Cquad" />
   </p>
<br/>

 E, finalmente, substituindo ```(7)``` em ```(6)```, obtemos:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24c_i%3D%5Cfrac%7B1%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%7D%5Ccdot%28x_i-%5Cbar%7Bx%7D%29%3D%5Cfrac%7B%28x_i-%5Cbar%7Bx%7D%29%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2%7D" />
   </p>

<br/>

 Concluímos, então, que o estimador linear não viesado e de variância minima para <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbeta_1"/> é:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24B%3D%5Csum%5Climits_%7Bi%3D1%7D%5Enc_iy_i%3D%5Cfrac%7B%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29yi%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2%7D"/>
   </p>
<br/>

que é o estimador de _MQO_ de <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbeta_1"/>. A demonstração para <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbeta_0"/> é análoga.

<br/>

## Análise da Variância

<br/>
Decomposição das Somas de Quadrados.
<br/>

Temos que:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20y_i-%5Cbar%7By%7D%26%3Dy_i-%5Chat%7By_i%7D&plus;%5Chat%7By_i%7D-%5Cbar%7By%7D%5C%5C%20y_i-%5Cbar%7By%7D%26%3D%5Chat%7B%5Cepsilon_i%7D&plus;%5Chat%7By_i%7D-%5Cbar%7By%7D%20%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%287%29%7D%5Cquad%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

Em que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cepsilon_i"/> são os resídos.
<br/>

Elevando ambos os membros de ```(1)``` ao quadrado e fazendo o somátorio de ```1``` até ```n```, obtemos:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20%5Csum%5Climits_%7Bi%3D1%7D%5En%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29%5E2%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5B%5Chat%7B%5Cepsilon_i%7D&plus;%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29%5D%5E2%5C%5C%20%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D&plus;2%5Csum%5Climits_%7Bi%3D1%7D%5En%5Cepsilon_i%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29&plus;%5Csum%5Climits_%7Bi%3D1%7D%5En%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29%5E2%20%5Cend%7Balign*%7D"/>
   </p>
   
   </br>

Vamos mostrar que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29%3D0"/>.

<br/>

De fato,
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D%5Chat%7By_i%7D-%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D%5Cbar%7By%7D%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D%5Chat%7By_i%7D-%5Cbar%7By%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%5Cepsilon_i%5C%5C%20%5CRightarrow%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%5Cepsilon_i%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%28y_i-%5Chat%7By%7D%29%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5By_i-%28%5Chat%5Cbeta_0&plus;%5Chat%5Cbeta_1x_i%29%5D%5C%5C%20%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5Eny_i-n%5Chat%5Cbeta_0-%5Chat%5Cbeta_1%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%5C%5C%20%5CRightarrow%20%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%5Cepsilon_i%5Chat%7By_i%7D%26%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%5Cepsilon_i%28%5Chat%5Cbeta_0&plus;%5Chat%5Cbeta_1x_i%29%3D%5Chat%5Cbeta_0%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%5Cepsilon_i&plus;%5Chat%5Cbeta_1%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%5Cepsilon_ix_i%5C%5C%20%5Chat%5Cbeta_1%5Csum%5Climits_%7Bi%3D1%7D%5En%28y_i-%5Chat%7By_i%7D%29x_i%26%3D%5Chat%5Cbeta_1%7B%5Cleft%5C%7B%5Csum%5Climits_%7Bi%3D1%7D%5En%5By_ix_i-%28%5Chat%5Cbeta_0&plus;%5Chat%5Cbeta_1x_i%29x_i%5D%5Cright%5C%7D%7D%5C%5C%20%26%3D%5Chat%5Cbeta_1%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5En%28y_ix_i-%5Chat%5Cbeta_0x_i&plus;%5Chat%5Cbeta_1x_i%5E2%29%5Cright%5D%5C%5C%20%5Cend%7Balign*%7D"/>
   </p>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5CRightarrow%5Chat%5Cbeta_1%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5Eny_ix_i%5Chat%5Cbeta_0%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i&plus;%5Chat%5Cbeta_1%5Csum%5Climits_%7Bi%3D1%7D%5Enx_i%5E2%5Cright%5D%3D0"/>
   </p>

Assim,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5Csum%5Climits_%7Bi%3D1%7D%5En%28y_i-%5Cbar%7By%7D%29%5E2%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%5Cepsilon_i%5E2&plus;%5Csum%5Climits_%7Bi%3D1%7D%5En%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29%5E2"/>
   </p>

<br/>

Essa relação mostra que a variação dos valores de ```y```, em torno de sua média <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbar%7By%7D"/>, pode ser dividida em duas partes:

<br/>

Uma que é explicada pela regressão,<img src="https://latex.codecogs.com/gif.latex?%5Ctiny%20%5Cleft%5B%5Csum%5Climits_%7Bi%3D1%7D%5En%28%5Chat%7By_i%7D-%5Cbar%7By%7D%29%5E2%5Cright%5D"/> e a outra <img src="https://latex.codecogs.com/gif.latex?%5Ctiny%20%24%24%5Cleft%28%5Csum%5Climits_%7Bi%3D1%7D%5En%20%5Chat%5Cepsilon_i%5E2%5Cright%29"/>, devido ao fato de que nem todos os pontos estão sobre a reta de regressão (que é a parte não explicada pela regressão). Ou seja, a _SQRes_ representa os diversos fatores não controlados ou explicados pelo modelo adotado.

<br/>

A soma dos quadrados dos resíduos tem ```(n-2)``` graus de liberdade, que obtemos por diferença ```(n-1)```:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%20%28n-1%29%3D%28n-2%29&plus;1"/>
   </p>

<br/>

ANOVA

F.V          |  G.L      |   SQ         |       QM   | F
:------------ | :---------: | :-------------:| :-----------:| :-------:
Regressão    |  1        | <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Chat%5Cbeta_2%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2"/> | <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cfrac%7BSQReg%7D%7B1%7D"/>| <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cfrac%7BQMReg%7D%7BQMRes%7D"/>
Resíduos     | ```n-2```     | Diferença | <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cfrac%7BSQRes%7D%7Bn-2%7D"/>|
TOTAL        | ```n-1```    | <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Csum%5Climits_%7Bi%3D1%7D%5En%28y_i-%5Cbar%7By%7D%29%5E2"/> |

 Temos que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20H_0%3D%5Cbeta_1"/>. Sob <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20H_0"/>, temos:

<br/>

01. <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cfrac%7BSQReg%7D%7B%5Csigma%5E2%7D%5Csim%5Cchi%5E2_%7B%281%29%7D"/>
<br/>

02. <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cfrac%7BSQRes%7D%7B%5Csigma%5E2%7D%5Csim%5Cchi%5E2_%7B%28n-2%29%7D"/>
<br/>

03. ```SQReg``` e ```SQRes``` são independentes.

<br/>

Segue que a estatística de teste:

<br/>

<p align="center">
<img src="https://latex.codecogs.com/gif.latex?F%3D%5Cfrac%7B%5Cfrac%7BSQReg%7D%7B%5Cfrac%7B%5Csigma%5E2%7D%7B1%7D%7D%7D%7B%5Cfrac%7BSQRes%7D%7B%5Cfrac%7B%5Csigma%5E2%7D%7B1%7D%7D%7D%20%3D%5Cfrac%7B%5Cfrac%7BSQReg%7D%7B%5Csigma%5E2%7D%7D%7B%5Cfrac%7BSQRes%7D%7B%5Csigma%5E2%7D%7D%20%3D%5Cfrac%7B%5Cchi%5E2_%7B%281%29%7D%7D%7B%5Cchi%5E2_%7B%28n-2%29%7D%7D%5Csim%20F_%7B%5B1%3B%28n-2%29%5D%7D"/>
   </p>
 
 <br/>
 
 Essa estatística pode ser usada para testar:

<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Csmall%20H_0%3A%5Cbeta_1%3D0%24%20contra%20%24H_1%3A%5Cbeta_1%5Cneq0"/>, ao nível de significância adotado.

<br/>

#### Modelo Linear Geral (Amostral)

<br/>

Consideremos uma amostra de ```n``` observações <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%28x_%7B1i%7D%2Cx_%7B2i%7D%2C...%2Cx_%7Bki%7D%3By_%7Bi%7D%29%24%20com%20%24i%3D1%2C...%2Cn"/>. O modelo linear geral é dado por:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20y_%7Bi%7D%20%3D%20%5Cbeta_%7B0%7D%20&plus;%20%5Cbeta_%7B1%7D%20x_%7B1i%7D%20&plus;%20...%20&plus;%20%5Cbeta_%7Bk%7Dx_%7Bki%7D%20&plus;%20%5Cepsilon_%7Bi%7D%2C%20%5Cquad%5Cmbox%7Bsendo%20que%20i%3D%201%2C%20...%2C%20n.%7D%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%281%29%7D%5Cquad"/>
   </p>

<br/>
Em que:
<br/>

- <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20E%5B%5Cvarepsilon_%7Bi%7D%5D%20%3D%200%2C%20%5Cforall_%7Bi%7D"/>; 
<br/>

- <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20y_i"/> é uma v.a. (só que observável);
<br/>

- <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20x_ji"/> é a variável não aleatória e observável pertencente a um domínio ```D```, com <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20j%20%3D%201%2C...%2Ck"/> e <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20i%20%3D%201%2C...%2Cn"/>; 
<br/>

- <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbeta_%7Bj%7D"/>, <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20j%20%3D%200%2C...%2Ck"/> são parâmetros desconhecidos e definidos em um espaço paramétrico;  
<br/>

- <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cepsilon_%7Bi%7D"/>'s são V.A.'s não observáveis, onde 
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24COV%5B%5Cvarepsilon_%7Bi%7D%2C%5Cvarepsilon_%7Bl%7D%5D%3D%5Csigma%5E2_%7Bil%7D%2C%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20i%20%3D%201%2C...%2Cn%20%5Cquad%5Cmbox%7Be%7D%5Cquad%20l%20%3D%201%2C...%2Cn"/>.
   </p>

<br/>

Em notação matricial, o modelo ```(1)``` fica dado por:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%24%24%5Cmathbf%7BY%3DX%5Cbeta&plus;%5Cepsilon%7D"/>
   </p>

<br/>

Sendo,
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cmathbf%7BY%7D%20%3D%20%5Cleft%5B%5Cbegin%7Bmatrix%7D%20y_%7B1%7D%5C%5C%20y_%7B2%7D%5C%5C%20%5Cvdots%5C%5C%20y_%7Bn%7D%20%5Cend%7Bmatrix%7D%5Cright%5D_%7Bn%5Ctimes1%7D%3B%20%5Cmathbf%7BX%7D%20%3D%20%5Cleft%5B%5Cbegin%7Bmatrix%7D%201%20%26%20x_%7B11%7D%20%26%20...%20%26%20x_%7Bk1%7D%20%5C%5C%201%20%26%20x_%7B12%7D%20%26%20...%20%26%20x_%7Bk2%7D%20%5C%5C%20%5Cvdots%20%26%5Cvdots%20%26%5Cddots%20%26%5Cvdots%5C%5C%201%20%26%20x_%7B1n%7D%20%26%20...%20%26%20x_%7Bkn%7D%20%5Cend%7Bmatrix%7D%5Cright%5D_%7Bn%5Ctimes%28k&plus;1%29%7D%3B%20%5Cmathbf%5Cbeta%20%3D%20%5Cleft%5B%5Cbegin%7Bmatrix%7D%20%5Cbeta_%7B0%7D%20%5C%5C%20%5Cbeta_%7B1%7D%20%5C%5C%20%5Cvdots%5C%5C%20%5Cbeta_%7Bk%7D%20%5Cend%7Bmatrix%7D%5Cright%5D_%7B%28k&plus;1%29%5Ctimes1%7D%3B%20%5Cmathbf%7B%5Cepsilon%7D%20%3D%20%5Cleft%5B%5Cbegin%7Bmatrix%7D%20%5Cepsilon_%7B1%7D%20%5C%5C%20%5Cepsilon_%7B2%7D%20%5C%5C%20%5Cvdots%5C%5C%20%5Cvarepsilon_%7Bn%7D%20%5Cend%7Bmatrix%7D%5Cright%5D_%7Bn%5Ctimes1%7D"/>
   </p>

<br/>

Em que:  
<br/>

- **```Y```** é um vetor aleatório <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%28n%5Ctimes%201%29"/>; 
<br/>

- **```X```** é a matriz <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%7Bn%5Ctimes%28k&plus;1%29%7D"/> de valores observáveis;  
<br/>

- <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cmathbf%7B%5Cbeta%7D"/> é um vetor <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5B%28k&plus;1%29%5Ctimes%201%5D"/> de parâmetros desconhecidos definidos e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5COmega_%5Cmathbf%7B%5Cbeta%7D"/>; 
<br/>

- <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Clarge%20%5Cmathbf%7B%5Cepsilon%7D"/> é um vetor aleatório tal que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5B%5Cepsilon%5D%3D0"/> e,
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BVar%5B%5Cepsilon%5D%3D%5CSigma%7D%20%3D%20%5Cleft%5B%5Cbegin%7Bmatrix%7D%20%7Bccc%7D%20Var%5B%5Cvarepsilon_%7B1%7D%5D%20%26%20Cov%5B%5Cvarepsilon_%7B1%7D%2C%5Cvarepsilon_%7B2%7D%5D%20%26%20...%20%26%20Cov%5B%5Cvarepsilon_%7B1%7D%2C%5Cvarepsilon_%7Bn%7D%5D%5C%5C%20Cov%5B%5Cvarepsilon_%7B2%7D%2C%5Cvarepsilon_%7B1%7D%5D%20%26%20Var%5B%5Cvarepsilon_%7B2%7D%5D%20%26%20...%20%26%20Cov%5B%5Cvarepsilon_%7B2%7D%2C%5Cvarepsilon_%7Bn%7D%5D%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cddots%20%26%20%5Cvdots%5C%5C%20Cov%5B%5Cvarepsilon_%7Bn%7D%2C%5Cvarepsilon_%7B1%7D%5D%20%26%20Cov%5B%5Cvarepsilon_%7Bn%7D%2C%5Cvarepsilon_%7B2%7D%5D%20%26%20...%20%26Var%5B%5Cvarepsilon_%7Bn%7D%5D%20%5Cend%7Bmatrix%7D%5Cright%5D"/>
   </p>
<br/>

**_OBS_**: Esse modelo admite vários casos especiais, dependendo:  
<br/>
1. da distribuição dos erros;  
2. da estrutura de covariância definida na matriz <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%5CSigma"/>;
3. do posto e da estrutura da matriz <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%7D"/>.

<br/>

**Exemplos:**  
<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20y%5Crightarrow"/> valor do aluguel (R$:50,00)  
<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20x%5Crightarrow"/> idade (anos)
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20y_i%3D%5Cbeta_0&plus;%5Cbeta_1x_i&plus;%5Cepsilon_i"/>
   </p>
<br/>

 Com <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5B%5Cepsilon_%7Bi%7D%5D%3D0"/>; <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Var%5B%5Cepsilon_%7Bi%7D%5D%3D%5Csigma%5E2"/>; <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20D%3D%7B5%5Cle%20X%20%5Cle%2020%7D"/>.

<br/>

Tomamos uma amostra de ```n=5``` observações: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20x_%7B1%7D%3D10%2Cx_%7B2%7D%3D13%2Cx_%7B3%7D%3D5%2Cx_%7B4%7D%3D7%2Cx_%7B5%7D%3D20"/>. Observou-se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20y_%7B1%7D%2C...%2Cy_%7B5%7D"/>. 
<br/>

Com base na amostra, podemos fazer inferências. Por exemplo, se ```x=8``` podemos estimar a média do valor do aluguel sem precisar 
<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20F_y%288%29%2C%20%5Cquad%5Cmbox%7Bpois%7D%5Cquad%5Cmbox%20x%3D8%20%5Cin%20D"/>.
<br/>

Podemos fazer <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5B%5Chat%7By%7D%7Cx%3D8%5D%3D%5Chat%7B%5Cbeta_0%7D%20&plus;%20%5Chat%7B%5Cbeta_1%7D%5Ccdot8"/>, em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%7B%5Cbeta_0%7D"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%7B%5Cbeta_%7B1%7D%7D"/> são os estimadores de M.Q.O.'s de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_0"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_1"/>, respectivamente.

<br/>

## Formas Quadráticas

<br/>

**Definição:** a função <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20f%28x_1%2C...%2Cx_n%29"/> de ```n``` variáveis reais <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20x_%7B1%7D%2C...%2Cx_%7Bn%7D"/> é uma forma quadrática se, a função 
<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20f%28x_%7B1%7D%2C...%2Cx_%7Bn%7D%29%3D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Csum%5Climits_%7Bj%3D1%7D%5Eka_%7Bij%7Dx_%7Bi%7Dx_%7Bj%7D%3D%5Cmathbf%7BX%5ETAX%7D."/>

<br/>

Com <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%7D%3D%28x_%7B1%7D%2C...%2Cx_%7Bn%7D%29%5ET"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BA%7D%3Da_%7Bij%7D"/>, onde esta é a matriz simétrica <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%28n%5Ctimes%20n%29"/> associada à forma quadrática.

<br/>

**-> Forma quadrática mais simples**: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20f%28x%29%3Da_%7B11%7Dx%5E2_%7B1%7D"/>.
<br/>

Formas quadráticas em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20x_%7B1%7D%2C...%2Cx_%7Bn%7D"/> são v.a.'s de extrema importância estatística.  
<br/>

*Exemplo*: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csum_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2%3D%5Csum_%7Bi%3D1%7D%5Enx%5E2_%7Bi%7D-n%5Cbar%7Bx%7D%5E2"/>.
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20*%20%5Csum%5Climits_%7Bi%3D1%7D%5Enx%5E2_%7Bi%7D%3D%5Cmathbf%7BX%5ETX%7D"/>
   </p>
   
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20*%20n%5Cbar%7Bx%7D%5E2%3D%20n%5Cleft%28%5Cfrac%7B1%7D%7Bn%7D%5Csum%5En_%7Bi%3D1%7Dx_%7Bi%7D%5Cright%29%5E2%3D%20%5Cfrac%7B1%7D%7Bn%7D%5Cleft%28%5Csum%5En_%7Bi%3D1%7Dx_%7Bi%7D%5Cright%29%5E2%3D%5Cfrac%7B1%7D%7Bn%7D%5B%5Cmathbf%7BX%5ET11X%7D%5D"/>
   </p>
   
<br/>

Portanto,
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_%7Bi%7D-%5Cbar%7Bx%7D%29%5E2%3D%5Cmathbf%7BX%5ETX%7D-%5Cfrac%7B1%7D%7Bn%7D%28%5Cmathbf%7BX%5ET11X%7D%29%3D%20%5Cmathbf%7BX%5ET%5Cleft%28I-%5Cfrac%7B1%7D%7Bn%7D11%5ET%5Cright%29X%7D%3D%5Cmathbf%7BX%5ETAX%7D."/>
   </p>

<br/>

**Classificação das Formas Quadráticas**  

<br/>

1. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ET%7D%5Ctextbf%7BAX%7D"/> é positiva definida se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ET%7D%5Ctextbf%7BAX%7D%3E0%24%2C%24%5Cforall%24%20%24%5Cmathbf%7BX%7D%5Cneq0"/>.

<br/>

2. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D"/> é positiva semidefinida se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D%5Cgeq0"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D%3D0"/> para, pelo menos, um <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20X%5Cneq0"/>.

<br/>

3. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D"/> é dita ser não negativa definida se for positiva definida ou positiva semidefinida.
<br/>

4. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D"/> é negativa definida se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D"/> é positiva definida. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D"/> é dita ser negativa se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETAX%7D"/> é positiva semidefinida.

<br/>

## Derivada de Formas Lineares e Quadráticas  

<br/>

**Definição:** Sejam <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%7D%3D%28x_%7B1%7D%2C...%2Cx_%7Bn%7D%29%5ET"/> e ```f(x)``` uma função real de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20x_%7B1%7D%2C...%2Cx_%7Bn%7D"/>. A derivada de ```f(.)``` com relação a <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20f%28%5Cmathbf%7BX%7D%29"/> é
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Cfrac%7B%5Cpartial%7Bf%28x%29%7D%7D%7B%5Cpartial%7BX%7D%7D%7D%3D%5Cleft%5B%5Cbegin%7Barray%7D%20%7Bccc%7D%20%5Cfrac%7B%5Cpartial%7Bf%28x%29%7D%7D%7B%5Cpartial%7BX_%7B1%7D%7D%7D%20%5C%5C%20%5Cfrac%7B%5Cpartial%7Bf%28x%29%7D%7D%7B%5Cpartial%7BX_%7B2%7D%7D%7D%20%5C%5C%20%5Cvdots%5C%5C%20%5Cfrac%7B%5Cpartial%7Bf%28x%29%7D%7D%7B%5Cpartial%7BX_%7Bn%7D%7D%7D%20%5Cend%7Barray%7D%5Cright%5D%2C%20%5Cquad%5Cmbox%7Bem%20que%7D%20%5C%20f%3A%20%5Cmathbb%7BR%7D%5En%5Crightarrow%5Cmathbb%7BR%7D%5Cquad"/>
   </p>

<br/>

**Teorema 1**: Se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7Ba%7D%24%3D%24%28a_%7B1%7D%2C...%2Ca_%7Bn%7D%29%5ET"/> é um vetor de constantes e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20f%28x%29%3D%5Cmathbf%7Ba%7D%5ET%5Ctextbf%7BX%7D%3D%5Cmathbf%7BX%7D%5ET%5Ctextbf%7Ba%7D"/> (função linear), 
<br/>

Então,

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cfrac%7B%5Cpartial%20f%28x%29%7D%7B%5Cpartial%20X%7D%3D%5Ctextbf%7Ba%7D"/>
   </p>
<br/>

**Teorema 2**: Se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20f%28X%29%3D%5Cmathbf%7BX%5ETAX%7D"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Ctextbf%7BA%7D"/> é a matriz de constantes, então:

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cfrac%7B%5Cpartial%20f%28x%29%7D%7B%5Cpartial%20X%7D%3D%5Ctextbf%7BX%7D%3D%202%5Ctextbf%7BAX%7D"/>
   </p>
<br/>

#### Esperança de um vetor aleatório

<br/>

Se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cmathbf%7BY%7D"/> é um vetor aleatório <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%28n%5Ctimes1%29"/>, onde <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cmathbf%7BY%7D%3D%28Y_1%2C...%2CY_n%29%5ET"/>, então
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5BY%5D%3D%5BE%28Y_1%29%2C...%2CE%28Y_n%29%5D%5ET"/>
   </p>
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BVar%5B%5Cmathbf%7BY%7D%5D%7D%3D%20%5Cleft%5B%5Cbegin%7Bmatrix%7D%20Var%5BY_%7B1%7D%5D%20%26%20Cov%5BY_%7B1%7D%2CY_%7B2%7D%5D%20%26%20...%20%26%20Cov%5BY_%7B1%7D%2CY_%7Bn%7D%5D%5C%5C%20Cov%5BY_%7B2%7D%2CY_%7B1%7D%5D%20%26%20Var%5BY_%7B2%7D%5D%20%26%20...%20%26%20Cov%5BY_%7B2%7D%2CY_%7Bn%7D%5D%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cddots%20%26%20%5Cvdots%5C%5C%20Cov%5BY_%7Bn%7D%2CY_%7B1%7D%5D%20%26%20Cov%5BY_%7Bn%7D%2CY_%7B2%7D%5D%20%26%20...%20%26Var%5BY_%7Bn%7D%5D%20%5Cend%7Bmatrix%7D%5Cright%5D"/>
   </p>
<br/>

Como a <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20COV%28Y_i%2CY_j%29%3DCOV%28Y_j%2CY_i%29"/>, então <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BVar%28Y%29%7D"> é uma matriz simétrica.

<br/>

**Propriedades:**
<br/>

Sejam <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BA%7D"/> uma matriz de constantes, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BY%7D"/> um vetor aleatório e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BW%3DAY%7D."/>
<br/>

*i)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5B%5Cmathbf%7BA%7D%5D%3D%5Cmathbf%7BA%7D"/>;
<br/>

*ii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5B%5Cmathbf%7BW%7D%5D%3D%20E%5B%5Cmathbf%7BAY%7D%5D%3D%5Cmathbf%7BAE%5BY%5D%7D"/>;
<br/>

*iii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20VAR%5B%5Cmathbf%7BW%7D%5D%3D%20VAR%5B%5Cmathbf%7BAY%7D%5D%3D%5Cmathbf%7BA%7DVAR%5B%5Cmathbf%7BY%5DA%5ET%7D"/>.

<br/>

## Modelo linear geral (Inferência)

<br/>

Considerar:

<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BY%3DX%5Cbeta%20&plus;%20%5Cepsilon%7D"/>, com <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Cepsilon%7D%20%5Csim%20N_n%28%5Cmathbf%7B0%7D%3B%5Csigma%5E2%5Cmathbf%7BI_n%7D%29"/>, onde <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csigma%5E2"/> é desconhecido.
<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20r%28%5Cmathbf%7BX%7D%29%3Dk&plus;1"/> (Posto completo)
<br/>

Daí,

<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BY%7D%20%5Csim%20N_n%28%5Cmathbf%7BX%5Cbeta%7D%2C%5Csigma%5E2%5Cmathbf%7BI_n%7D%29"/>
   </p>
<br/>

Suposições:
<br/>

*i)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5B%5Cmathbf%7B%5Cepsilon%7D%5D%3D%5Cmathbf%7B0%7D%20%5CRightarrow%20E%5B%5Cmathbf%7B%5Cepsilon_i%7D%5D%3D0%2C%20%5Cforall%20i%3D1%2C2%2C...%2Cn%3B"/>
<br/>

*ii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20VAR%5B%5Cmathbf%7B%5Cepsilon%7D%5D%3D%5Csigma%5E2%20%5Cmathbf%7BI_n%7D%5CRightarrow%20VAR%5B%5Cmathbf%7B%5Cepsilon_i%7D%5D%3D%5Csigma%5E2%3B%5Cforall_i"/> (Homocedasticidade);
<br/>

*iii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20COV%5B%5Cepsilon_i%2C%5Cepsilon_j%5D%3D0%2C%20%5Cforall%20%5C%20i%5Cneq%7Bj%7D."/>

<br/>

Como o vetor <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Clarge%20%5Cmathbf%7B%5Cepsilon%7D"> tem distribuição normal n-variada e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20COV%5B%5Cepsilon_i%2C%5Cepsilon_j%5D%3D0%24%20%24%5Cforall%20i%5Cneq%20j"/>, então <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Clarge%20%5Cepsilon_i"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cvarepsilon_j"/> são independentes.

<br/>

#### Estimação do vetor <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Cbeta%7D"/>

<br/>

Suponha que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BY%7D%5Csim%20N_n%28%5Cmathbf%7BX%20%5Cbeta%7D%3B%5Csigma%5E2%5Cmathbf%7BI_n%7D%29."/>

<br/>

A função de verossimilhança é dada por:
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20L%5Cbf%7B%28%5Cbeta%2C%5Csigma%5E2%2CY%2CX%29%7D%26%3D%5Cfrac%7B1%7D%7B%282%5Cpi%29%5E%5Cfrac%7Bn%7D%7B2%7D%28%5Csigma%5E2%29%5E%5Cfrac%7Bn%7D%7B2%7D%7D%20exp%5Cleft%5C%7B-%5Cfrac%7B1%7D%20%7B2%5Csigma%5E2%7D%20%5Cbf%7B%28Y-X%20%5Cbeta%29%5Et%28Y-X%20%5Cbeta%29%7D%5Cright%5C%7D%5C%5C%20%26%3D%20%7B%5Cleft%20%28%5Cfrac%7B1%7D%7B2%5Cpi%20%5Csigma%5E2%7D%5Cright%29%5E%5Cfrac%20n2%7Dexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%20%7B2%5Csigma%5E2%7D%20%5Cbf%7B%28Y-X%20%5Cbeta%29%5Et%28Y-X%20%5Cbeta%29%7D%5Cright%5C%7D%20%5Cend%7Balign*%7D"/>
   </p>
 
<br/>

O logaritimo da função de verossimilhança fica dado por:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20ln%5BL%28%5Cbeta%2C%5Csigma%5E2%2CY%2CX%29%5D%3D%5Cfrac%7Bn%7D%7B2%7D%20ln%20%5B2%5Cpi%20%5Csigma%5E2%5D-%20%5Cfrac%7B1%7D%7B2%5Csigma%5E2%7D%5Cbf%7B%28Y-X%20%5Cbeta%29%5ET%20%28Y-X%20%5Cbeta%29%7D"/>
   </p>
<br/>

Espaço paramétrico: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5CTheta%3D%5C%7B%28%5Cmathbf%7B%5Cbeta%7D%2C%5Csigma%5E2%29%3A%5Csigma%5E2%3E0%2C%20-%5Cinfty%5Cle%5Cmathbf%7B%5Cbeta%7D%5Cle%5Cinfty%5C%7D%7D"/>.

<br/>

Encontrando os estimadores de Máxima Verossimilhança para <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%5Cbeta%7D"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csigma%5E2"/>.

<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cfrac%7B%5Cpartial%20ln%20%5BL%28%5Cbeta%2C%5Csigma%5E2%2CY%2CX%29%5D%7D%7B%5Cpartial%20%5Cbeta%7D%26%3D-%5Cfrac%7B1%7D%7B2%5Csigma%5E2%7D%20%5Cbf%7B%5B2X%5ET%20Y-2X%5ETX%5Cbeta%5D%7D%5C%5C%20%26%3D-%5Cfrac%7B1%7D%7B%5Csigma%5E2%7D%5B%5Cbf%7BX%5ETY-X%5ETX%5Cbeta%7D%5D%5C%5C%20%5Cfrac%7B%5Cpartial%20ln%20%5BL%5Cbf%7B%28%5Cbeta%2C%5Csigma%5E2%2CY%2CX%29%5D%7D%7D%7B%5Cpartial%20%5Cbeta%7D%26%3D0%5CRightarrow%20-%5Cfrac%7B1%7D%7B%5Csigma%5E2%7D%20%5Cbf%7B%5BX%5ETY-X%5ETX%5Chat%7B%5Cbeta%7D%5D%7D%3D0%5C%5C%20%5CRightarrow%20%5Cbf%7BX%5ETY-X%5ETX%5Chat%7B%5Cbeta%7D%7D%26%3D0%20%5CRightarrow%20%5Cbf%7BX%5ETY%3DX%5ETX%5Chat%7B%5Cbeta%7D%7D%5C%5C%20%5CRightarrow%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETY%7D%26%3D%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETX%5Cbf%7B%5Chat%7B%5Cbeta%7D%7D%7D%5C%5C%20%5CRightarrow%20%5Cbf%7B%5Chat%7B%5Cbeta%7D%7D%26%3D%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETY%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

Agora, iremos encontrar os estimador de Máxima Verossimilhança para <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csigma%5E2"/>:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cfrac%7B%5Cpartial%20ln%20%5BL%5Cbf%7B%28%5Cbeta%2C%5Csigma%5E2%2CY%2CX%29%5D%7D%7D%7B%5Cpartial%20%5Csigma%5E2%7D%26%3D-%5Cfrac%7Bn%7D%7B2%7D%5Ccdot%5Cfrac%7B1%7D%7B2%5Cpi%20%5Csigma%5E2%7D%5Ccdot2%5Cpi&plus;%5Cfrac%7B1%7D%7B2%5Csigma%5E4%7D%5Cbf%7B%28Y-X%5Cbeta%29%5ET%20%28Y-X%5Cbeta%29%7D%5C%5C%20%5Cpartial%20ln%20%5BL%5Cbf%7B%28%5Cbeta%2C%5Csigma%5E2%2CY%2CX%29%5D%7D%26%3D0%20%5CRightarrow%20-%5Cfrac%7Bn%7D%7B2%5Chat%7B%5Csigma%7D%5E2%7D&plus;%5Cfrac%7B1%7D%7B2%5Chat%7B%5Csigma%7D%5E4%7D%28Y-%5Cbf%7BX%7D%5Chat%7B%5Cbeta%7D%29%5ET%28Y-%5Cbf%7BX%5Chat%7B%5Cbeta%7D%7D%29%3D0%5C%5C%20%5CRightarrow%20%5Cfrac%7Bn%7D%7B2%5Chat%7B%5Csigma%7D%5E2%7D%26%3D%5Cfrac%7B1%7D%7B2%5Chat%7B%5Csigma%7D%5E4%7D%5Cbf%7B%28Y-X%5Chat%7B%5Cbeta%7D%29%5ET%28Y-X%5Chat%7B%5Cbeta%7D%29%7D%5C%5C%20%5CRightarrow%20%5Cfrac%7Bn%7D%7B2%7D%26%3D%5Cfrac%7B1%7D%7B2%5Chat%7B%5Csigma%7D%5E2%7D%5Cbf%7B%28Y-X%5Chat%7B%5Cbeta%7D%29%5ET%20%28Y-X%5Chat%7B%5Cbeta%7D%29%7D%5C%5C%20%5CRightarrow%20n%26%3D%5Cfrac%7B1%7D%7B%5Chat%7B%5Csigma%7D%5E2%7D%5Cbf%7B%28Y-X%5Chat%7B%5Cbeta%7D%29%5ET%20%28Y-X%5Chat%7B%5Cbeta%7D%29%7D%5C%5C%20%5CRightarrow%20%5Chat%7B%5Csigma%7D%5E2%26%3D%5Cfrac%7B1%7D%7Bn%7D%5Cbf%7B%28Y-X%5Chat%7B%5Cbeta%7D%29%5ET%20%28Y-X%5Chat%7B%5Cbeta%7D%29%7D%20%5Cend%7Balign*%7D"/>
   </p>
<br/>

**Ou**

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cmathbf%7B%5Chat%7B%5Csigma%7D%5E2%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D%5E2%7D"/>
   </p>
<br/>

Em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Chat%7B%5Csigma%7D%5E2%3D%5Cfrac%7B1%7D%7Bn%7D%5Csum%5Climits_%7Bi%3D1%7D%5En%5Chat%7B%5Cepsilon_i%7D%5E2%7D"/>**=** **_SQRes_**.
<br/>

O vetor de médias <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Cmu%7D%3D%28%5Cmu_1%2C...%2C%5Cmu_n%29%5ET"/> é estimado por <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%7B%5Cmu%7D%3D%5Cbf%7BX%5Chat%7B%5Cbeta%7D%7D"/>, ou seja:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%5Chat%7B%5Cmu%7D%3DX%28X%5ETX%29%5E%7B-1%7DX%5ETY%20%3D%20HY%7D"/>
   </p>
<br/>

Em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BH%3DX%7D%28X%5ETX%29%5E%7B-1%7DX"/> é chamado de "matriz _HAT_" e representa a matriz de projeção ortogonal do <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbb%7BR%7D%5En"/> sobre o subspaço vetorial gerado pelas colunas da matriz <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BX%7D"/>.
<br/>

_OBS_: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BH%7D"/> é simétrica e idempotente.

<br/>

i. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BH%3DH%5ET%7D"/> (<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BH%7D"/> é simetrica).
<br/>

De fato,
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%5BX%28X%5ET%20X%29%5E%7B-1%7D%20X%5D%5ET%20%3DX%28X%5ETX%29%5E%7B-1%7DX%3DH%7D"/>
   </p>

<br/>

ii. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%20H%5ETH%7D%3D%20H"/> (<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BH%7D"/> é idempotente).

<br/>

De fato,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cbf%7BHH%7D%26%3D%20%5Cbf%7B%7B%5BX%28X%5ETX%29%5E%7B-1%7DX%5ET%5D%7D%7B%5BX%28X%5ETX%29%5E%7B-1%7DX%5ET%5D%7D%7D%5C%5C%20%26%3D%20%5Cbf%7BX%28X%5ETX%29%5E%7B-1%7DX%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ET%7D%5C%5C%20%26%3D%20%5Cbf%7BX%28X%5ETX%29%5E%7B-1%7DX%5ET%3DH%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

#### Residuos e Propriedades
<br/>
  
O resíduo ordinário associado à ```i-ésima``` observação é dado por

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%7B%5Cepsilon_i%7D%3D%20Y_i-%5Chat%7BY%7D%3D%5Chat%7BY%7D-%5Chat%7B%5Cmu_i%7D"/>
   </p>
<br/>

A partir de agora, chamaremos este resíduo por <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20r_i"/>. Consideremos:
<br/>

  <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20r%3D%28r_1%2C...r_n%29%5ET"/>
   </p>
  <br/>
  
Daí, segue que:
<br/>

  <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7Br%3DY-X%5Chat%7B%5Cbeta%7D%3DY-%5Chat%7B%5Cmu%7D%3DY-HY%3D%28I-H%29Y%7D"/>
   </p>
  
<br/>
  
**Propriedades:**

 <br/>
 
1. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7Dr_i%3D0%5CRightarrow%5Csum_%7Bi%3D1%7D%5E%7Bn%7Dr_i%3D%7B1%5ETr%3D1%5ET%28I-H%29Y%7D%3D%281%5ET-1%5ETH%29Y"/>
  <br/>
  
Agora, defina:
  <br/>
  
  
  <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BX%7D%3D%20%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bcccc%7D%201%20%26%20x_%7B11%7D%20%26%20%5Ccdots%20%26%20x_%7Bk1%7D%5C%5C%201%20%26%20x_%7B12%7D%20%26%20%5Ccdots%20%26%20x_%7Bk2%7D%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cddots%20%26%20%5Cvdots%5C%5C%201%20%26%20x_%7B1n%7D%20%26%20%5Ccdots%20%26%20x_%7Bkn%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%20%3D%20%5B1%2CX_1%5D%2C%5Cquad%5Cmbox%7Bem%20que%7D"/>
   </p>
  
  <br/>
  
  <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%7BX_1%7D%3D%20%5Cleft%5B%20%5Cbegin%7Bmatrix%7D%20x_%7B11%7D%20%26%20%5Ccdots%20%26%20x_%7Bk1%7D%5C%5C%20x_%7B12%7D%20%26%20%5Ccdots%20%26%20x_%7Bk2%7D%5C%5C%20%5Cvdots%20%26%20%5Cddots%20%26%20%5Cvdots%5C%5C%20x_%7B1n%7D%20%26%20%5Ccdots%20%26%20x_%7Bkn%7D%5C%5C%20%5Cend%7Bmatrix%7D%20%5Cright%5D.%20%5Cquad%5Cmbox%7BNeste%20caso%2C%7D%7D"/>
   </p>
  
  <br/>
  
  <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cbf%7BX%5ET%7D%3D%20%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbf%7B1%5ET%7D%5C%5C%20%5Cbf%7BX_%7B1%7D%7B%5ET%7D%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%3B%20%5Cbf%7BX%5ET%20H%20%3D%20X%5ET%20X%20%28X%5ET%20X%29%5E%7B-1%7D%20X%5ET%7D%20%26%3D%20%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbf%7B1%5ET%7D%5C%5C%20%5Cbf%7BX_%7B1%7D%7B%5ET%7D%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%5Cbf%7BX%20%28X%5ET%20X%29%5E%7B-1%7D%20X%5ET%7D%20%5C%5C%20%26%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbf%7B1%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ET%7D%5C%5C%20%5Cbf%7BX_1%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ET%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%20%5Cend%7Balign*%7D"/>
   </p>
  
  <br/>
  
 Como,
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BX%5ETH%7D%3DX%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ET%3DX%5Et%3D%20%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbf%7B1%5ET%7D%5C%5C%20%5Cbf%7BX_%7B1%7D%7B%5ET%7D%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%5Cquad%5Cquad%5Cquad%5Cquad%5Cquad%5Cquad%5Cmbox%7B%5Cbf%7B%281%29%7D%7D"/>
   </p>

<br/>

Então, por **```(1)```**, temos que
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BX%5ETH%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbf1%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ET%5C%5C%20%5Cbf%7BX_1%5ET%28X%5ETX%29%5E%7B-1%7DX%5ET%7D%20%5Cend%7Barray%7D%20%5Cright%5D%3D%20%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbf%7B1%5ET%7D%5C%5C%20%5Cbf%7BX_1%5ET%7D%20%5Cend%7Barray%7D%20%5Cright%5D"/>
   </p>

<br/>

Isto implica que,
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B1%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ET%3D1%5ET%7D%5CRightarrow%5C%201%5ETH%3D1%5ET"/>
   </p>

<br/>

Como,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B1%5ETH%3D1%5ET%7D%5Cmbox%7B%2C%20segue%20que%3A%7D%20%5Csum%5Climits_%7Bi%3D1%7D%5Enr_i%3D%5Cbf%281%5ET-1%5ETH%29Y%3D%281%5ET-1%5ET%29Y%3D0Y%3D0"/>
   </p>

<br/>

2. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BX%5ETr%7D%3De"/>
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cbf%7BX%5ETr%7D%3D%20%5Cbf%7BX%5ET%28I-H%29Y%7D%20%26%3D%20%5Cbf%7BX%5ET%28Y-HY%29%3DX%5ETY-X%5ETHY%7D%5C%5C%20%26%3D%20%5Cbf%7BX%5ETY-X%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ETY%7D%5C%5C%20%26%3D%20%5Cbf%7BX%5ETY-X%5ETY%3D0%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>
3. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Chat%7BY%7D%5ETr%7D%3D0"/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cbf%7B%5Chat%7BY%7D%5ETr%7D%3D%5Cbf%7B%28X%5Chat%7B%5Cbeta%7D%29%5ET%28I-H%29Y%7D%20%26%3D%20%5Cbf%7B%5Chat%7B%5Cbeta%7D%5ETX%5ET%28I-H%29Y%7D%5C%5C%20%26%3D%20%5Cbf%7B%5Chat%7B%5Cbeta%7D%5ETX%5ET%28Y-HY%29%7D%5C%5C%20%26%3D%20%5Cbf%7B%5Chat%7B%5Cbeta%7D%5ETX%5ETY-%5Chat%7B%5Cbeta%7D%5ETX%5ETHY%7D%5C%5C%20%26%3D%20%5Cbf%7B%5Chat%7B%5Cbeta%7DX%5ETY-%5Chat%7B%5Cbeta%7D%5ETX%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ETY%7D%5C%5C%20%26%3D%5Cbf%7B%5Chat%7B%5Cbeta%7DX%5ETY-%5Chat%7B%5Cbeta%7D%5ETX%5ETY%3D0%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

4. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%7B%5Cbeta%7D"/> é um estimador não viesado para <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%5Cbeta%7D."/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20E%5Cbf%7B%5B%5Chat%5Cbeta%5D%7D%26%3D%20%5Cbf%7BE%5B%28X%5ETX%29%5E%7B-1%7DX%5ETY%5D%7D%5C%5C%20%26%3D%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETE%5BY%5D%7D%5C%5C%20%26%3D%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETX%5Cbeta%7D%3DI%5Cbeta%3D%5Cbeta%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

5. A matriz de covariâncias de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%7B%5Cbeta%7D"/> é <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csigma%5E2%5Cmathbf%7B%28X%5ETX%29%5E%7B-1%7D%7D."/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20Var%5B%5Chat%7B%5Cbeta%7D%5D%3DVar%5B%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETY%7D%5D%20%26%3D%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%7D%5C%5C%20Var%5BY%5D%5Cbf%7BX%28X%5ETX%29%5E%7B-1%7D%7D%26%3D%5Cbf%7BX%28X%5ETX%29%5E%7B-1%7DX%5ET%7D%5Csigma%5E2%5Cbf%7BX%28X%5ETX%29%5E%7B1%7D%7D%5C%5C%20%26%3D%5Csigma%5E2%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETX%28X%5ETX%29%5E%7B-1%7D%7D%5C%5C%20%26%3D%5Csigma%5E2%5Cbf%7B%28X%5ETX%29%5E%7B-1%7D%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

6. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%7B%5Chat%7B%5Cbeta%7D%7D%5Csim%20N_%7Bk&plus;1%7D%5B%5Cbf%7B%5Cbeta%3B%5Csigma%5E2%5Cbf%7B%28X%5ETX%29%5E%7B-1%7D%7D%7D%5D%7D"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%7B%5Cbeta%7D_j%5Csim%20N_p%28%5Cbeta_j%3Ba_%7Bij%7D%5C%20%5Csigma%5E2%29"/>, em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20a_%7Bij%7D"/> é o elemento ```jj``` da matriz <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7D%7D."/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%28X%5ETX%29%5E%7B-1%7D%7D%3D%5Cleft%5B%20%5Cbegin%7Bmatrix%7D%20a_%7B00%7D%20%26%20a_%7B01%7D%20%26%20%5Ccdots%20%26%20a_%7B0k%7D%5C%5C%20a_%7B10%7D%20%26%20a_%7B11%7D%20%26%20%5Ccdots%20%26%20a_%7B1k%7D%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cddots%20%26%20%5Cvdots%5C%5C%20a_%7Bk0%7D%20%26%20a_%7Bk1%7D%20%26%20%5Ccdots%20%26%20a_%7Bkk%7D%5C%5C%20%5Cend%7Bmatrix%7D%20%5Cright%5D"/>
   </p>
  
  <br/>
  
**_OBS_**: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_i"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_j"/> são independentes <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5CLeftrightarrow%20a_%7Bij%7D%3D0%5C%20%5Cforall%5C%20i%5Cneq%20j."/>

<br/>

#### **Decomposição das somas de quadrados**

<br/>


<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQT%3D%20%5Csum%5Climits_%7Bi%3D1%7D%5En%28Y_i-%5Cbar%7BY%7D%29%3D%5Csum%5Climits_%7Bi%3D1%7D%5EnY_i%5E2-n%5Cbar%7BY%7D%5E2%5Cquad%5Cquad%5Cmbox%7B%281%29%7D%5C%5C%20%5Csum%5Climits_%7Bi%3D1%7D%5EnY_i%5E2%3D%20%5Cbf%7BY%5ETY%7D%3DY%5ETIY%3DY%5ET%28I&plus;H-H%29Y"/>
   </p>
<br/>
Onde,
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BH%3DX%28X%5ETX%29%5E%7B-1%7DX%5ET%7D%3D%20%5Cbf%7BY%5ET%5B%28I-H%29&plus;H%5DY%7D%3D%20%5Cbf%7BY%5ET%28I-H%29Y&plus;Y%5ETHY%7D"/>
   </p>

<br/>

Como <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BH%7D"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%28I-H%29%7D"> são simétricas e idempotentes, temos:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cbf%7BY%5ETY%7D%20%26%3D%20%5Cbf%7BY%5ET%28I-H%29%28I-H%29Y&plus;Y%5ETHHY%7D%5C%5C%20%26%3D%20%5Cbf%7BY%5ET%28I-H%29%5ET%28I-H%29Y&plus;Y%5ETH%5ETHY%7D%5C%5C%20%26%3D%20%5Cbf%7B%5BY%28I-H%29%5D%5ET%5B%28I-H%29Y%5D&plus;%5BYH%5D%5ET%5BHY%5D%7D%20%5Cend%7Balign*%7D"/>
   </p>
<br/>

Daí, 
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BY%5ETY%3Dr%5ETr&plus;%5Chat%7Bu%7D%5ET%5Chat%7Bu%7D%7D%5Cquad%5Cquad%5Cquad%5Cquad%5Cmbox%7B%282%29%7D"/>
   </p>
<br/>

Observe que,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Chat%7Bu%7D%5ET%5Chat%7Bu%7D%3DY%5ETHHY%3DY%5ETHY%3DY%5ETX%28X%5ETX%29%5E%7B-1%7DX%5ETY%3DY%5ETX%5Chat%7B%5Cbeta%7D%7D%5Cquad%5Cquad%5Cquad%5Cquad%5Cmbox%7B%283%29%7D"/>
   </p>
          
<br/>

De ```(2)``` e ```(3)```, segue que:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BY%5ETY%3Dr%5ETr&plus;Y%5ETX%5Chat%7B%5Cbeta%7D%7D"/>
   </p>

<br/>

Desta forma,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQT%3D%5Csum%5Climits_%7Bi%3D1%7D%5EnY_i%5E2-n%5Cbar%7BY%7D%5E2%3D%5Cmathbf%7BY%5ETY-n%5Cbar%7BY%7D%5E2%3Dr%5ETr&plus;Y%5ETX%5Chat%7B%5Cbeta%7D-n%5Cbar%7BY%7D%5E2%7D"/>
   </p>

<br/>

Observemos que:

<br/>

*i)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQT%3D%5Cmathbf%7BY%5ETY-n%5Cbar%7BY%7D%5E2%3DY%5ETY-%5Cfrac%7B1%7D%7Bn%7DY%5ET11%5ETY%3DY%5ET%5Cleft%5BI-%5Cfrac%7B1%7D%7Bn%7D11%5ET%5Cright%5DY%3DY%5ET%5Cleft%5BI-%5Cfrac%7B1%7D%7Bn%7DJ_n%5Cright%5DY%7D"/>

<br/>

Em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20J_n%3D%5Cmathbf%7B11%5ET%7D%3B"/>

<br/>

*ii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQReg%3D%5Cmathbf%7BY%5ETX%5Chat%7B%5Cbeta%7D-n%5Cbar%7BY%7D%5E2%3DY%5ETHY-%5Cfrac%7B1%7D%7Bn%7DY%5ETJ_nY%3DY%5ET%5BH-%5Cfrac%7B1%7D%7Bn%7DJ_n%5DY%7D%3B"/>

<br/>

*iii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQRes%3D%5Cmathbf%7Br%5ETr%3DY%5ET%28I-H%29Y%7D."/>

<br/>

**RESUMO:**

<br/>
<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQT%3D%5Cmathbf%7BY%5ETY-n%5Cbar%7BY%7D%5E2%7D%3B"/>
<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQReg%3D%5Cmathbf%7BY%5ETY%5Chat%7B%5Cbeta%7D-n%5Cbar%7BY%7D%5E2%7D%3B"/>
<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20SQRes%3D%5Cmathbf%7Br%5ETr%7D"/>

<br/>

**Resultado 01:** Se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BA%7D"/> é uma matriz <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20n%5Ctimes%20m"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BA%5E2%3DmA%7D"/>, <br/>

Então: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Tr%28%5Cbf%7BA%7D%29%3Dmr%28A%29"/>

<br/>

Se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BA%7D"/> é idempotente, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20m%3D1"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Tr%28%5Cmathbf%7BA%7D%29%3Dr%28%5Cmathbf%7BA%7D%29."/>

<br/>

**Resultado 02:** Sejam <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BA%7D"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BB%7D"/> matrizes <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20m%5Ctimes%20n"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20m%5Ctimes%20m"/>, respectivamente. Então, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BTr%28AB%29%3DTr%28BA%29%7D."/>

<br/>

**Tabela da Análise de Variância (ANOVA)**

F.V          |  G.L      |   SQ         |       QM   | <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BF_%7BTab%7D%7D"/>
:------------ | :---------: | :-------------:| :-----------:| :-------:
Regressão    |  ```k```        | <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7B%5Chat%5Cbeta%5E2X%5ETY-n%5Cbar%7BY%7D%5E2%7D"/> | <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7BSQReg%7D%7Bk%7D"/> | <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7BQMReg%7D%7BQMRes%7D"/>
Resíduos     | ```n-k-1```     | <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BY%5ETY-%5Chat%7B%5Cbeta%7D%5ETX%5ETY%7D"/> | <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7BSQRes%7D%7Bn-k-1%7D"/>|
TOTAL        | ```n-1```      | <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Y%5ETY-n%5Cbar%7BY%7D%5E2"/> |

<br/>

Sob a hipótese de que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7B%5Cbeta%5E*%7D%3D%28%5Cbeta_1%2C...%2C%5Cbeta_k%29%5ET%3D%5Cmathbf%7B0%7D"/>, temos:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20F%3D%5Cfrac%7BQMReg%7D%7BQMRes%7D%5Csim%20F_%7B%5Bk%3Bn-k-1%5D%7D"/>
   </p>

<br/>

**Teste:** <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0%3A%5Cbeta_1%3D%5Cbeta_2%3D...%3D%5Cbeta_k%3D0"/> contra <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_1%3A"/> Pelo menos um dos <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta_i"/>'s é não nulo.

<br/>

**_Regra de Decisão_**: Rejeitar <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0"/> se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20F_%7BCal%7D%5Cge%20F_%7BTab%7D"/>. Em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20F_%7BTab%7D"/> é tal que
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20P%5BF_%7B%5Bk%3Bn-k-1%5D%7D%5Cge%20F_%7BTab%7D%5D%3D%5Calpha"/>
   </p>

<br/>

_OBS_: Este teste verifica a importancia da inclusão <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%28x_1%2C...%2Cx_k%29"/> no modelo.

<br/>

#### Teste - Hipótese Linear Geral

<br/>

EX: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Y%3D%5Cbeta_0&plus;%5Cbeta_1X_1&plus;%5Cbeta_2X_2&plus;%5Cbeta_3X_3&plus;%5Cbeta_4X_4&plus;%5Cepsilon"/>

<br/>

_HIPÓTESES:_

<br/>

*i)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0%3A%5Cbeta_2%3D0%2C%5C%20%5Cbeta_4%3D0%20%5CLeftrightarrow%20%5Cbf%7BC%5Cbeta%7D%3Dm"/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BC%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bccccc%7D%200%20%26%200%20%26%201%20%26%200%20%26%200%5C%5C%200%20%26%200%20%26%200%20%26%200%20%26%201%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%3B%20%5Cbf%7Bm%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%200%5C%5C%20%5Cbf%7B0%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D"/>
   </p>
<br/>

Sob <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0"/>, o modelo fica <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Y%3D%5Cbeta_0&plus;%5Cbeta_1X_1&plus;%5Cbeta_3X_3&plus;%5Cepsilon">: 

<br/>

*ii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0%3A%5Cbeta_1&plus;%5Cbeta_3%3D0%20%5CLeftrightarrow%20%5Cbf%7BC%5Cbeta%7D%3Dm"/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BC%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bccccc%7D%200%20%26%201%20%26%200%20%26%201%20%26%200%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%3B%20%5Cbf%7Bm%7D%3D0"/>
   </p>
<br/>

Sob <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0"/>, o modelo fica:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20Y%26%3D%5Cbeta_0&plus;%5Cbeta_1X_1&plus;%5Cbeta_2X_2-%5Cbeta_1X_3&plus;%5Cbeta_4X_4&plus;%5Cepsilon%5C%5C%20%26%3D%5Cbeta_0&plus;%5Cbeta_1%28X_1-X_3%29&plus;%5Cbeta_2X_2&plus;%5Cbeta_4X_4&plus;%5Cepsilon%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

*iii)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0%3A%5Cbeta_2%2C%5C%20%5Cbeta_3%3D6"/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BC%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bccccc%7D%200%20%26%200%20%26%201%20%26%200%20%26%200%5C%5C%200%20%26%200%20%26%200%20%26%201%20%26%200%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%3B%20%5Cbf%7Bm%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%202%5C%5C%20%5Cbf%7B6%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D"/>
   </p>
<br/>

Sob <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0"/>,

<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20Y%26%3D%5Cbeta_0&plus;%5Cbeta_1X_1&plus;2X_2&plus;6X_3&plus;%5Cbeta_4X_4&plus;%5Cepsilon%5C%5C%20%26%3D%5Cbeta_0&plus;2X_2&plus;6X_3&plus;%5Cbeta_1X_1&plus;%5Cbeta_4X_4&plus;%5Cepsilon%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

*iv)* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0%3A%5Cbeta_1%3D%5Cbeta_2%3D%5Cbeta_3%3D%5Cbeta_4%3D0%20%5CLeftrightarrow%20%5Cbf%7BC%5Cbeta%3Dm%7D"/>
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_0%3A%5Cbeta_1%3D%5Cbeta_2%3D%5Cbeta_3%3D%5Cbeta_4%3D0%20%5CLeftrightarrow%20%5Cleft%20%5C%7B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbeta_1-%5Cbeta_2%3D0%5C%5C%20%5Cbeta_1-%5Cbeta_3%3D0%5C%5C%20%5Cbeta_1-%5Cbeta_4%3D0%5C%5C%20%5Cend%7Barray%7D%20%5Cright."/>
   </p>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BC%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bccccc%7D%200%20%26%201%20%26%20-1%20%26%200%20%26%200%5C%5C%200%20%26%201%20%26%200%20%26%20-1%20%26%200%5C%5C%200%20%26%201%20%26%200%20%26%200%20%26%20-1%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%3B%20%5Cbf%7Bm%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%200%5C%5C%200%5C%5C%200%20%5Cend%7Barray%7D%20%5Cright%5D"/>

<br/>

**Ou** 

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cleft%20%5C%7B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cbeta_1-%5Cbeta_2%3D0%5C%5C%20%5Cbeta_1-%5Cbeta_3%3D0%5C%5C%20%5Cbeta_1-%5Cbeta_4%3D0%5C%5C%20%5Cend%7Barray%7D%20%5Cright.%20%5CLeftrightarrow%20%5Cbf%7BC%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bccccc%7D%200%20%26%201%20%26%20-1%20%26%200%20%26%200%5C%5C%200%20%26%201%20%26%200%20%26%20-1%20%26%200%5C%5C%200%20%26%201%20%26%200%20%26%200%20%26%20-1%5C%5C%20%5Cend%7Barray%7D%20%5Cright%5D%3B%20%5Cbf%7Bm%7D%3D%5Cleft%5B%20%5Cbegin%7Barray%7D%7Bc%7D%200%5C%5C%200%5C%5C%200%20%5Cend%7Barray%7D%20%5Cright%5D"/>
   </p>

<br/>

**_OBS_**: A matriz <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BC%7D"/> e o vetor <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7Bm%7D"/> não, necessariamente, são iguais.

<br/>

Queremos testar hipóteses do tipo:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Bcases%7D%20H_0%3A%20%5Cbf%7BC%5Cbeta%7D%3Dm%5C%5C%20H_1%3A%20%5Cbf%7BC%5Cbeta%7D%5Cneq%20m%5C%5C%20%5Cend%7Bcases%7D%5CRightarrow%20%5Cmakebox%7BHipotese%20linear%20geral%7D"/>
   </p>

<br/>

A matriz <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BC%7D"/> é <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20p%5Ctimes%20%28k&plus;1%29"/> de constantes
<br/>
<br/>

*1.*<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cquad%20r%28%5Cmathbf%7BC%7D%29%3Dp%3Ck&plus;1"/>, ```p``` é o número de hipóteses;
<br/>

*2.* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BC%7D"/> é o posto completo e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7Bm%7D"/> é um vetor <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20p%5Ctimes%201."/>

<br/>

## Teste da razão de Verossimilhança Generalizada (_TRVG_)

<br/>

Seja <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20L%28%5Cmathbf%7B%5Ctheta%7D%3Bx_%7B1%7D%2C%20%5Cldots%2Cx_%7Bn%7D%29%2C"/> a função de verossimilhança com base de uma amostra <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20x_%7B1%7D%2C%20%5Cldots%2Cx_%7Bn%7D%2C%5Cmathbf%7B%5Ctheta%7D%20%5Cin%20%5CTheta"/>. Para testar:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cleft%20%5C%7B%20%5Cbegin%7Barray%7D%7Bc%7D%20H_%7B0%7D%3A%5Cmathbf%7B%5Ctheta%7D%5Cin%20%5CTheta_%7B0%7D%5Csubset%20%5CTheta%5C%5C%20H_%7B1%7D%3A%5Cmathbf%7B%5Ctheta%7D%5Cin%20%5CTheta%20-%20%5CTheta_%7B0%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright."/>
   </p>
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Clarge%20%5Clambda%3D%5Clambda%28x_%7B1%7D%2C%20%5Cldots%2Cx_%7Bn%7D%29%3D%5Cfrac%7B%5Coverset%7BmaXL%28%5Cmathbf%7B%5Ctheta%7D%3Bx_%7B1%7D%2C%20%5Cldots%2Cx_%7Bn%7D%29%7D%7B%5Cscriptsize%7B%5Ctheta%7D%5Cin%20%5CTheta_%7B0%7D%7D%7D%7B%7B%5Coverset%7BmaXL%28%5Cmathbf%7B%5Ctheta%7D%3Bx_%7B1%7D%2C%20%5Cldots%2Cx_%7Bn%7D%29%7D%7B%5Cscriptsize%7B%5Ctheta%7D%5Cin%20%5CTheta%7D%7D%7D"/>
   </p>

<br/>

Que é chamada de _razão de verossimilhança generalizada_ (R.V.G.).

<br/>

O teste da R.V.G. rejeita <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_%7B0%7D"/>, se <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda%5Cleq%5Clambda_%7B0%7D"/> em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%200%5Cleq%5Clambda_%7B0%7D%5Cleq1"/> é tal que
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20P%5B%5Clambda%28X_%7B1%7D%2C%20%5Cldots%2CX_%7Bn%7D%29%5Cleq%5Clambda_%7B0%7D%7CH_%7B0%7D%20%5Ctextrm%7B%20verdadeiro%20%7D%5D%3D%20%5Calpha"/>
   </p>

<br/>

Para testar as hipóteses: <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cleft%20%5C%7B%20%5Cbegin%7Barray%7D%7Bc%7D%20H_%7B0%7D%3A%5Cmathbf%7BC%7D%5Cmathbf%7B%5Cbeta%7D%3D%5Cmathbf%7Bm%7D%5C%5C%20H_%7B1%7D%3A%5Cmathbf%7BC%7D%5Cmathbf%7B%5Cbeta%7D%5Cneq%5Cmathbf%7Bm%7D%5C%5C%20%5Cend%7Barray%7D%20%5Cright."/>
   </p>

<br/> 

Temos:
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20L%28%5Cbeta%2C%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%20%5Cmathbf%7BX%7D%29%3D%20%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5C%7D"/>
   </p>
<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cbf%7B%5CTheta%3D%5C%7B%7B%28%5Cmathbf%7B%5Cbeta%7D%2C%5Csigma%5E%7B2%7D%29%2C-%5Cinfty%20%3C%20%5Cbeta_%7Bj%7D%3C%5Cinfty%2C%5Csigma%5E%7B2%7D%3E0%2C%20j%3D0%2C%20%5Cldots%2Ck%7D%5C%7D%7D"/>
<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Cbf%7B%5CTheta_%7B0%7D%3D%7B%5C%7B%28%5Cbeta%2C%5Csigma%5E%7B2%7D%29%5Cin%20%5CTheta%7CC%5Cbeta%7D%3Dm%7D%5C%7D"/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%7B%5Coverset%7BmaXL%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%7D%7B%5Cscriptsize%7B%28%5Cmathbf%5Cbeta%2C%5Csigma%5E%7B2%7D%29%5Cin%20%5CTheta%7D%7D%7D%20%26%3D%20L%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5C%5C%20%26%3D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Chat%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Chat%5Cbeta%7D%29%5Cright%5C%7D%5C%5C%20%26%3D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7Dn%5Csigma%5E%7B2%7D%5Cright%5C%7D%5C%5C%20%26%3D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7Bn%7D%7B2%7D%5Cright%5C%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

Em que, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csigma%5E%7B2%7D%3D%5Cfrac%7B1%7D%7Bn%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29."/>

<br/>

O objetivo agora é maximizar <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20L%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29"/> sujeito à restrição <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7BC%7D%5Cmathbf%7B%5Cbeta%7D%3D%5Cmathbf%7Bm%7D."/> Para isso, usaremos os multiplicadores de Lagrange.

<br/>

Seja <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20L%3DL%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29-%5Cmathbf%7Bn%7D%5E%7BT%7D%28%5Cmathbf%7BC%7D%5Cmathbf%7B%5Cbeta%7D%3D%5Cmathbf%7Bm%7D%29"/>, em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmathbf%7Bn%7D%5E%7BT%7D"/> é o vetor <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20P%5Ctimes%201"/> de multiplicadores de Lagrange.

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%20%5Cbeta%7D%26%3DL%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5Cleft%5B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28-2%7B%5Cmathbf%7BX%7D%5E%7BT%7D%7D&plus;2%7B%5Cmathbf%7BX%7D%5E%7BT%7D%7D%7B%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%7D%29%5Cright%5D-%7B%5Cmathbf%7BC%7D%5E%7BT%7D%7B%5Cmathbf%7Bn%7D%7D%7D%5C%5C%20%26%3D-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28%7B%5Cmathbf%7BX%7D%5E%7BT%7D%7D%7B%5Cmathbf%7BX%7D%7B%5Cmathbf%7B%5Cbeta%7D%7D-%7B%5Cmathbf%7BX%7D%5E%7BT%7D%7D%7B%5Cmathbf%7By%7D%29L%28%5Cmathbf%7B%5Cbeta%7D%2C%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29-%7B%5Cmathbf%7BC%7D%5E%7BT%7D%7B%5Cmathbf%7Bn%7D%7D%7D%7D%7D%5C%5C%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%5Csigma%5E%7B2%7D%7D%26%3D%5Cfrac%7Bn%7D%7B2%7D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D-1%7D%5Cleft%28-%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B4%7D%7D%7D%5Cright%29%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5C%7D%5C%5C%20%26&plus;%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5C%7D%5Cleft%28%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B4%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%29%5C%5C%20%5Cend%7Balign*%7D"/>
   </p>
 <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%26%3D%5Cfrac%7Bn%7D%7B2%7D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B-1%7D%5Cleft%28-%5Cfrac%7B1%7D%7B2%7B%5CPi%7D%7B%5Csigma%5E%7B4%7D%7D%7D%5Cright%29L%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29&plus;L%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B4%7D%7D%5Cleft%5B%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5D%5C%5C%20%26%3DL%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5Cleft%5B-%5Cfrac%7Bn%7D%7B2%5Csigma%5E%7B2%7D%7D&plus;%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B4%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5D%5C%5C%20%26%3D%5Cfrac%7B1%7D%7B2%5Cpi%5E%7B2%7D%7DL%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5Cleft%5B-%20n&plus;%5Cfrac%7B1%7D%7B%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5D%20%5Cend%7Balign*%7D"/>
   </p>   
<br/>
<br/>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%5Csigma%5E%7B2%7D%7D%26%3D%5Cfrac%7Bn%7D%7B2%7D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D-1%7D%5Cleft%28-%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B4%7D%7D%7D%5Cright%29%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5C%7D%5C%5C%20%26&plus;%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5C%7D%5Cleft%28%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B4%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%29%5C%5C%20%26%3D%5Cfrac%7Bn%7D%7B2%7D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B2%7D%7D%7D%5Cright%29%5E%7B-1%7D%5Cleft%28-%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Csigma%5E%7B4%7D%7D%7D%5Cright%29L%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29&plus;L%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B4%7D%7D%5Cleft%5B%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5D%5C%5C%20%5Cend%7Balign*%7D"/>
</p>
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%26%3DL%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5Cleft%5B-%5Cfrac%7Bn%7D%7B2%5Csigma%5E%7B2%7D%7D&plus;%5Cfrac%7B1%7D%7B2%5Csigma%5E%7B4%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5D%5C%5C%20%26%3D%5Cfrac%7B1%7D%7B2%5Cpi%5E%7B2%7D%7DL%28%5Cmathbf%7B%5Cbeta%7D%2C%20%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%5Cleft%5B-%20n&plus;%5Cfrac%7B1%7D%7B%5Csigma%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Cbeta%7D%29%5Cright%5D%20%5Cend%7Balign*%7D"/>
   </p>
   
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%20n%7D%3D-%28%5Cmathbf%7BC%7D%5Cmathbf%7B%5Cbeta%7D-%5Cmathbf%7Bm%7D%29%20%5Cend%7Balign*%7D"/>
   </p>
   
<br/>

Igualando as derivadas a zero:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%20%5Csigma%5E2%7D%3D0"/>
   </p>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5CRightarrow%5Cfrac%7B1%7D%7B2%5Chat%5Csigma_%7B0%7D%5E%7B2%7D%7D%5Cleft%28-%20n&plus;%5Cfrac%7B1%7D%7B%5Chat%5Csigma_%7B0%7D%5E%7B2%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta_%7B0%7D%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta%7D_%7B0%7D%29%5Cright%29%5Ccdot%20L%28%5Chat%7B%5Cbeta_%7B0%7D%7D%2C%20%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%3D0%5C%5C%20%5CRightarrow-n&plus;%5Cfrac%7B1%7D%7B%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta_%7B0%7D%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta%7D_%7B0%7D%29%3D0%5C%5C%20%5CRightarrow%5Cfrac%7B1%7D%7B%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta_%7B0%7D%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta%7D_%7B0%7D%29%3Dn%5C%5C%20%5CRightarrow%20n%7B%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%7D%3D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta_%7B0%7D%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta%7D_%7B0%7D%29%5C%5C%20%5CRightarrow%20%7B%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%7D%3D%5Cfrac%7B1%7D%7Bn%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta_%7B0%7D%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%7B%5Chat%5Cbeta%7D_%7B0%7D%29%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%7B%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%7D"/> sob <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%7BH_%7B0%7D%7D"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%5Cbeta_%7B0%7D"/> é o E.M.V. de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbeta"/> sob <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20H_%7B0%7D."/>

<br/>

Temos ainda que,

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%20%5Cbeta%7D%3D0%5CRightarrow-%5Cfrac%7B1%7D%7B%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%7D%28%5Cmathbf%7BX%7D%5E%7BT%7D%5Cmathbf%7BX%7D%5Chat%5Cbeta_%7B0%7D-%5Cmathbf%7BX%7D%5E%7BT%7D%5Cmathbf%7By%7D%29%5Ccdot%20L%28%5Chat%7B%5Cbeta_%7B0%7D%7D%2C%20%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29-%7B%5Cmathbf%7BC%7D%5E%7BT%7D%5Chat%7Bn%7D_%7B0%7D%7D%3D0"/>
   </p>
   
<br/>

Dividindo ambos os lados da igualdade por  <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20L%28%5Chat%7B%5Cbeta_%7B0%7D%7D%2C%20%5Chat%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29"/>, obtemos:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5CRightarrow-%5Cfrac%7B1%7D%7B%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%7D%28%5Cmathbf%7BX%7D%5E%7BT%7D%5Cmathbf%7BX%7D%5Chat%5Cbeta_%7B0%7D-%5Cmathbf%7BX%7D%5E%7BT%7D%5Cmathbf%7By%7D%29-%5Cfrac%7B%5Cmathbf%7BC%7D%5E%7BT%7D%5Chat%7Bn%7D_%7B0%7D%7D%7BL%28%5Chat%7B%5Cbeta_%7B0%7D%7D%2C%20%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%7D%3D0"/>
   </p>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5CRightarrow-%28%5Cmathbf%7BX%7D%5E%7BT%7D%5Cmathbf%7BX%7D%5Chat%5Cbeta_%7B0%7D-%5Cmathbf%7BX%7D%5E%7BT%7D%5Cmathbf%7By%7D%29%3D%5Cfrac%7B%5Cmathbf%7B%5Csigma_%7B0%7D%5E2%20C%7D%5E%7BT%7D%5Chat%7Bn%7D_%7B0%7D%7D%7BL%28%5Chat%7B%5Cbeta_%7B0%7D%7D%2C%20%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%7D"/>
   </p>

<br/>

Temos:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7BX%5ETX%5Chat%7B%5Cbeta_0%7D-X%5ETy&plus;C%5ETn%5E*%7D"/>
   </p>
Sabendo que:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbf%7Bn%5E*%7D%3D%7B%5Cfrac%7B%5Chat%7B%5Csigma_0%7D%5E2%5Chat%7Bn_0%7D%7D%7BL%28%5Chat%7B%5Cbeta_%7B0%7D%7D%2C%20%5Chat%5Csigma%5E%7B2%7D_%7B0%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%7D%7D"/>
   </p>

<br/>

Então:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5CRightarrow%20%5Cbf%7BX%5ETX%5Chat%7B%5Cbeta_0%7D%7D%20%26%3D%20%5Cbf%7BX%5ETX-C%5ETn%5E*%7D%5Ccdot%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7D%7D%5C%5C%20%5CRightarrow%20%5Cbf%7B%5Chat%7B%5Cbeta_0%7D%7D%20%26%3D%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7D%5BX%5ETy-C%5ETn%5E*%5D%7D%5C%5C%20%26%3D%20%5Cbf%7B%28X%5ETX%29%5E%7B-1%7DX%5ETy-%28X%5ETX%29%5E%7B-1%7DC%5ETn%5E*%7D%5C%5C%20%26%3D%20%5Cbf%7B%5Chat%7B%5Cbeta%7D-%28X%5ETX%29%5E%7B-1%7DCn%5E*%7D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%20%5Cbf%20n%7D%3D0%5Crightarrow%20%7B%5Cbf%20C%7D%20%7B%5Cbf%20%7B%5Chat%20%5Cbeta%7D%7D%5E0%3D%20%5Cbf%20m"/>
   </p>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Crightarrow%20%5Cbf%7BC%7D%5B%5Cbf%7B%5Chat%7B%5Cbeta%7D%7D-%28%5Cbf%7BX%5ETX%7D%29%5E%7B-1%7DC%5ET%20n%5E*%5D%26%3Dm%5C%5C%20%5Crightarrow%20%7B%5Cbf%20C%7D%20%7B%5Cbf%20%5Chat%7B%5Cbeta%7D%7D-%20%7B%5Cbf%20C%7D%28%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%29%7D%5E%7B-1%7D%20%7B%5Cbf%20C%7D%5ET%20%7B%5Cbf%20n%7D%5E*%20%26%3D%20%7B%5Cbf%20m%7D%20%5Cend%7Balign*%7D"/>
   </p>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Crightarrow%20%7B%5Cbf%20C%7D%28%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%7D%29%5E%7B-1%7D%7B%5Cbf%20C%7D%5ET%20%7B%5Cbf%20n%7D%5E*%3D%20%7B%5Cbf%20C%7D%20%7B%5Cbf%20%5Chat%7B%5Cbeta%7D%7D-%20%7B%5Cbf%20m%7D"/>
   </p>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5B%7B%5Cbf%20C%7D%28%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%7D%29%5E%7B-1%7D%20%7B%5Cbf%20C%7D%5ET%5D%5E%7B-1%7D%20%7B%5Cbf%20C%7D%28%20%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%7D%29%5E%7B-1%7D%7B%5Cbf%7BC%5ET%7D%7D%20%7B%5Cbf%20n%7D%5E*%3D%5B%7B%5Cbf%20C%7D%28%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%7D%29%5E%7B-1%7D%20%7B%5Cbf%20C%7D%5ET%5D%5E%7B-1%7D%5B%20%7B%5Cbf%20C%7D%20%5Cbf%7B%5Chat%7B%5Cbeta%7D%7D-%20%5Cmathbf%20m%5D%5C%5C%20%7B%5Cbf%20%5Chat%7Bn%7D%7D%5E*%3D%5B%20%7B%5Cbf%20C%7D%28%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%7D%29%5E%7B-1%7D%20%7B%5Cbf%20C%7D%5ET%5D%5E%7B-1%7D%5B%7B%5Cbf%20C%7D%7B%5Chat%7B%5Cbeta%7D%7D-%7B%20%5Cbf%20m%7D%5D%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

Substituindo <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%7B%5Cbf%20%5Chat%7Bn%7D%7D%5E*"/> em ```(1)```, obtemos:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%7B%5Cbf%20%5Chat%20%7B%5Cbeta%5E0%7D%7D%3D%7B%5Cbf%20%5Chat%7B%5Cbeta%7D%7D-%28%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%7D%29%5E%7B-1%7D%5B%7B%5Cbf%20C%7D%28%7B%5Cbf%20X%7D%5ET%20%7B%5Cbf%20X%7D%29%5E%7B-1%7D%20%7B%5Cbf%20C%7D%5ET%5D%5E%7B-1%7D%5B%7B%5Cbf%20C%7D%20%7B%5Cbf%20%5Chat%7B%5Cbeta%7D%7D-%7B%5Cbf%20m%7D%5D"/>
   </p>
<br/>

Finalmente, o <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%7B%5Coverset%7BmaXL%28%5Cmathbf%7B%5Cbeta%7D%2C%5Csigma%5E%7B2%7D%3B%5Cmathbf%7By%7D%2C%5Cmathbf%7BX%7D%29%7D%7B%5Cscriptsize%7B%5Cmathbf%5CTheta%5Cin%20%5CTheta%7D%7D%7D"/> é

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20L%28%5Chat%20%5Cbeta%5E0%2C%5Csigma%5E2%3B%7B%5Cbf%20y%7D%2C%20%7B%5Cbf%20X%7D%29%26%3D%20%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Chat%7B%5Csigma_0%7D%5E2%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7B1%7D%7B2%5Chat%7B%5Csigma_0%7D%5E2%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Chat%7B%5Cbeta%5E0%7D%7D%29%5E%7BT%7D%28%5Cmathbf%7By%7D-%5Cmathbf%7BX%7D%5Cmathbf%7B%5Chat%7B%5Cbeta%5E0%7D%7D%29%5Cright%5C%7D%5C%5C%20%26%3D%5Cleft%28%5Cfrac%7B1%7D%7B2%7B%5Cpi%7D%7B%5Chat%7B%5Csigma_0%7D%5E2%7D%7D%5Cright%29%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cexp%5Cleft%5C%7B-%5Cfrac%7Bn%7D%7B2%5Chat%7B%5Csigma_0%7D%5E2%7D%5Cmathbf%7B%5Chat%7B%5Csigma_0%5E2%7D%7D%5Cright%5C%7D%5C%5C%20%26%3D%5Cleft%28%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2_0%7D%5Cright%29%5E%5Cfrac%7Bn%7D%7B2%7D%20exp%5Cleft%28-%5Cfrac%7Bn%7D%7B2%7D%5Cright%29%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

Vamos obter, agora, a estatística de teste da R.V.G:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda%3D%5Cfrac%7B%20%5Cleft%5B%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2_0%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7Dexp%5Cleft%5B%5Cfrac%7B-n%7D%7B2%7D%5Cright%5D%7D%7B%5Cleft%5B%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7Dexp%5Cleft%5B%5Cfrac%7B-n%7D%7B2%7D%5Cright%5D%7D%20%3D%5Cfrac%7B%5Cleft%5B%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2_0%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D%7D%20%7B%5Cleft%5B%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D%7D"/>
   </p>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda%3D%5Cfrac%7B%20%5Cleft%5B%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2_0%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D%7D%7B%5Cleft%5B%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2%7D%5Cright%5D%7D%20%3D%5Cfrac%7B%5Cleft%5B%5Cfrac%7B1%7D%7B%5Chat%20%5Csigma_0%5E2%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D%7D%20%7B%5Cleft%5B%5Cfrac%7B1%7D%7B2%5Cpi%20%5Chat%20%5Csigma%5E2%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D%7D%3D%20%5Cleft%20%5B%5Cfrac%7B%5Chat%5Csigma%5E2%7D%7B%5Chat%5Csigma%5E2_0%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D"/>
   </p>

<br/>

Em que,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%20%5Csigma%5E2%3D%5Cfrac%7B1%7D%7Bn%7D%28%7B%5Cbf%20y%7D-%7B%5Cbf%20X%7D%20%5Chat%20%7B%5Cbf%20%5Cbeta%7D%29%5ET%28%7B%5Cbf%20y%7D-%7B%5Cbf%20X%7D%20%5Chat%20%5Cbeta%29"/>
   </p>
   
<br/>

e
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Chat%20%5Csigma%5E2_0%3D%5Cfrac%7B1%7D%7Bn%7D%28%7B%5Cbf%20y%7D-%7B%5Cbf%20X%7D%20%7B%5Cbf%20%5Chat%20%5Cbeta%7D_0%29%5ET%28%7B%5Cbf%20y%7D-%7B%5Cbf%20X%7D%20%7B%5Cbf%20%5Chat%20%5Cbeta%7D_0%29"/>
   </p>

<br/>

Região crítica: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda%3D%5Cleft%20%5B%5Cfrac%7B%5Chat%5Csigma%5E2%7D%7B%5Chat%20%5Csigma%5E2_0%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D%20%5Cleq%20%5Clambda_c"/>

<br/>

Para obter <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda_c"/> devemos obter a distribuição de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda%3D%5Cleft%20%5B%5Cfrac%7B%5Chat%5Csigma%5E2%7D%7B%5Chat%20%5Csigma%5E2_0%7D%5Cright%5D%5E%5Cfrac%7Bn%7D%7B2%7D"/>. Para isto, vamos usar a estatística <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20W%3D%28%5Clambda%5E%5Cfrac%7B-2%7D%7Bn%7D-1%29%20%5Cleft%28%5Cfrac%7Bn-k-1%7D%7Bp%7D%5Cright%29"/>:

<br/>

Temos que:

<br/>

* ```W``` é uma função monótona de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda"/>;

<br/>

* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20%5Clambda%5Cleq%5Clambda_0%20%26%5CLeftrightarrow%20%5Clambda%5E%7B-1%7D%20%5Cgeq%20%5Clambda_0%5E%7B-1%7D%20%5CLeftrightarrow%20%5Clambda%5E%7B-%5Cfrac%7B2%7D%7Bn%7D%7D%20%5Cgeq%20%5Clambda_0%5E%7B-%5Cfrac%7B2%7D%7Bn%7D%7D%20%5C%5C%20%26%5CLeftrightarrow%20%28%5Clambda%5E%7B-%5Cfrac%7B2%7D%7Bn%7D%7D-1%29%5Cleft%28%5Cfrac%7Bn-k-1%7D%7Bp%7D%5Cright%29%5Cgeq%20%28%5Clambda%5E%7B-%5Cfrac%7B2%7D%7Bn%7D%7D_0-1%29%5Cleft%28%5Cfrac%7Bn-k-1%7D%7Bp%7D%5Cright%29%5C%5C%20%26%5CLeftrightarrow%20W%20%5Cgeq%20W_0%20%5Cend%7Balign*%7D"/>

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cbegin%7Balign*%7D%20W%3D%28%5Clambda%5E%7B-%5Cfrac%7B2%7D%7Bn%7D%7D-1%29%5Cleft%28%5Cfrac%7Bn-k-1%7D%7Bp%7D%5Cright%29%20%26%3D%20%5Cleft%5B%5Cleft%5B%5Cleft%5C%7B%7B%5Cfrac%7B%5Chat%20%5Csigma%5E2%7D%7B%5Chat%20%5Csigma%5E2_0%7D%7D%5Cright%5C%7D%5E%7B%5Cfrac%7Bn%7D%7B2%7D%7D%5Cright%5D%5E%7B-%5Cfrac%7B2%7D%7Bn%7D%7D-1%5Cright%5D%5Cleft%28%5Cfrac%7Bn-k-1%7D%7Bp%7D%5Cright%29%5C%5C%20%26%3D%20%5Cleft%20%28%5Cfrac%7B%5Chat%20%5Csigma%5E2_0%7D%7B%5Chat%5Csigma%5E2%7D-1%5Cright%29%5Cleft%28%5Cfrac%7Bn-k-1%7D%7Bp%7D%5Cright%29%5C%5C%20%26%3D%20%5Cleft%28%5Cfrac%7B%5Chat%20%5Csigma%5E2_0-%20%5Chat%20%5Csigma%5E2%7D%7B%5Chat%20%5Csigma%5E2%7D%5Cright%29%5Ctimes%20%5Cleft%20%28%5Cfrac%7Bn-k-1%7D%7Bp%7D%5Cright%29%20%5Cend%7Balign*%7D"/>
   </p>

<br/>

Segue que a distribuição de ```W``` é <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cchi%5E2_%7B%28p%2Cr%29%7D"/>. Ou melhor:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7B%5B%7B%5Cbf%20C%7D%20%7B%5Cbf%20%5Chat%5Cbeta%7D%20-%7B%5Cbf%20m%7D%5D%5ET%5B%7B%5Cbf%20C%7D%28%7B%5Cbf%20X%7D%5ET%7B%5Cbf%20X%7D%29%5E%7B-1%7D%7B%5Cbf%20C%7D%5ET%29%5E%7B-1%7D%5D%28%7B%5Cbf%20C%7D%20%7B%5Cbf%20%5Chat%5Cbeta%7D-%7B%5Cbf%20m%7D%29%7D%7B%5Csigma%5E2%7D%20%5Csim%5Cchi%5E2_%7B%28p%2Cr%29%7D"/>
   </p>

<br/>

## **Modelos Lineares Generalizados**

<br/>

**_Introdução_**

<br>

O modelo de regressão normal linear tem o problema de ser utilizado quando o fenômeno sob o estudo não apresenta uma resposta, para o qual é razoável a suposição de normalidade. Uma saída é fazer transformação na variável resposta, com o objetivo de obter uma "nova variável" que seja normalmente distribuída. 
<br/>

#### Transformações utilizadas

<br/>

* <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Csqrt%28y%29%24%3B%20%24log%28y%29"/>

<br/>

* Transformação _Box e Cox_ (1964)
<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20y%5E*%3D%20%5Cleft%20%5C%7B%20%5Cbegin%7Barray%7D%7Bc%7D%20%5Cfrac%7By%5E%5Clambda-1%7D%7B%5Clambda%7D%5C%5C%20log%28y%29%5C%5C%20%5Cend%7Barray%7D%2C%20%5Cmbox%7Bsendo%7D%20%5C%20%7B%5Clambda%7D%20%5C%20%5Cmbox%7Buma%20constante%20desconhecida%7D%20%5Cright."/>
   </p>

<br/>

Espera-se com essa transformação:

<br/>

1. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20y%5E*"/> possua distribuição aproximadamente normal;

<br/>

2. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Var%28y%5E*%29"/> seja constante;

<br/>

3. <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%28y%5E*%29%3D%5Cbeta_0&plus;%5Cbeta_1X_1&plus;...&plus;%5Cbeta_kX_k%3D%5Ceta"/>

<br/>

Verificou-se, no entanto, que isso raramente ocorria para um mesmo valor de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Clambda"/> _(Box and Draper, 1987)_.	

<br/>

Com o avanço computacional, outros modelos começaram a ser mais utilizados. No entanto, uma das propostas mais interessantes foi de _Nelder_ e _Wedderborn_ (1972), que propuseram os modelos lineares generalizados. 
<br/>

A ideia consistia em dar mais opções para distribuição da variável resposta e flexibilizar a relação funcional entre a média da variável resposta e o preditor linear <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Ceta"/>.

<br/>

**_Definição_**
<br/>

Os Modelos Lineares Generalizados são definidos a partir de duas componentes: a componente sistemática e a componente aleatória.

<br/>

**_Componente Sistemática_**
<br/>

* _Preditor Linear_: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Ceta_i%3D%7B%5Cbf%20X%7D%5ET_i%20%7B%5Cbf%5Cbeta%7D%2C%20%7B%5Cbf%20%5Cbeta%7D%5ET%3D%28%5Cbeta_1%2C...%2C%5Cbeta_p%29%5ET."/> <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20P%3Cn"/> é um vetor de parâmetros desconhecidos a serem estimados, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%7B%5Cbf%20x_i%7D%3D%28x_i1%2C...%2Cx_ip%29%5ET."/>

<br/>

* _Função de ligação_: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20g%28%5Cmu_i%29%3D%5Ceta_i"/>, função bijetora, em que ```g(.)``` é uma função monótona diferenciável.

<br/>

**_Componente Aleatória_** 
<br/>

Para uma amostra <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Y_1%2CY_2%2C...%2CY_n"/> de variáveis aleatórias independentes com médias <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmu_1%24%2C%20%24%5Cmu_2%24%2C...%2C%20%24%5Cmu_n"/>. Considera-se que a distribuição de <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Y_i"/> pertença a família exponencial de distribuições.

<br/>

#### **_Família Exponencial_** 

<br/>

Consideramos <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Y_1%2CY_2%2C...%2CY_n"/> variáveis indenpendentes com função de densidade de probabilidade (ou função de probabilidade) dada por:

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20f_y%28y_i%3B%5Ctheta_i%2C%5Cphi%29%3Dexp%5C%7B%5Cphi%5By_i%5Ctheta_i-b%28%5Ctheta_i%29%5D&plus;c%28y_i%2C%5Cphi%29%5C%7D"/>
   </p>

<br/>

Em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7B1%7D%7B%5Cphi%7D"/> é o parâmetro de dispersão (<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cphi"/> é o parâmetro de precisão, <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cphi%20%3E%200"/>); ```b(.)``` e ```c(.)``` são funções contínuas diferenciáveis; <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Ctheta_i"/> é o parâmetro natural (canônico).

<br/>

**_Notação:_** <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Y_i%20%5Cin"/> Família Exponencial (<img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cmu_i%3B%5Cphi"/>)

<br/>

* Casos especiais: 
<br/>

1- O modelo clássico de regressão linear com erro normal. 
<br/>

2- O modelo logístico para análise de dados envolvendo proporções.
<br/>

3- O modelo de teste de vida (Análise de Sobrevivência).
<br/>

Sob condições usuais de regularidade:
 <br/>
 
 <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5Cleft%5C%7B%5Cfrac%7B%5Cpartial%20%5Clog%5Bf_y%28y_i%3B%5Ctheta_i%2C%5Cphi%29%5D%7D%7B%5Cpartial%20%5Ctheta_i%7D%5Cright%5C%7D%3D0%20%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%281%29%7D"/>
   </p>
 
  <br/>
  
  e
  <br/>
  
 <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5Cleft%5C%7B%5Cfrac%7B%5Cpartial%5E2%20%5Clog%5Bf_y%28y_i%3B%5Ctheta_i%2C%5Cphi%29%5D%7D%7B%5Cpartial%20%5Ctheta_i%5E2%7D%5Cright%5C%7D%3D-%20E%5Cleft%5C%7B%5Cfrac%7B%5Cpartial%20%5Clog%5Bf_y%28y_i%3B%5Ctheta_i%2C%5Cphi%29%5D%7D%7B%5Cpartial%20%5Ctheta_i%7D%5Cright%5C%7D%5E2%5Cquad%5Cmbox%7B%7D%5Cquad%5Cquad%20%5Cqquad%5Cmbox%7B%282%29%7D"/>
   </p>

<br/>

Segue que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%28Y_i%29%3D%5Cmu_i%3Db%27%28%5Ctheta_i%29"/> e <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20Var%28Y_i%29%3D%28%5Cphi%5E%7B-1%7D%29"/>, em que <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20V%28%5Cmu_i%29%3D%5Cfrac%7Bd%5Cmu_i%7D%7Bd%5Ctheta_i%7D"/> é a função de variância.

<br/>

De fato:

<br/>

Seja 
<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20L%3Dlogf_y%28y_i%3B%5Ctheta_i%2C%5Cphi%29%5C%5C"/>
   </p>
   
 <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20L%3D%5Cphi%5By_i%5Ctheta_i-b%28%5Ctheta_i%29%5D&plus;c%28y_i%3B%5Cphi%29%5C%5C"/>
   </p>
   
  <p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%20%5Ctheta_i%7D%3D%5Cphi%5By_i-b%27%28%5Ctheta_i%29%5D"/>
   </p>   

<br/>

De ```(1)``` temos que: <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%20%5Cleft%5B%5Cfrac%7B%5Cpartial%20L%7D%7B%5Cpartial%20%5Ctheta_i%7D%5Cright%5D%3D0."/> Logo,

<br/>

<p align="center">
   <img src="https://latex.codecogs.com/gif.latex?%5Cinline%20%5Csmall%20E%5B%5Cphi%28y_i-b%27%28%5Ctheta_i%29%29%5D%3D0%20%5CLongleftrightarrow%20E%5By_i%5D%3Db%27%28%5Ctheta_i%29"/>
   </p>

<br/>
