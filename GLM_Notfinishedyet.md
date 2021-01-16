# Generalized-Linear-Models_Classes



## title: "Modelos Lineares Generalizados"
## authors: "Class of 2017.1"
## date: "10 de Novembro"
## output: html_document


<br/>
<br/>
<div align="right">
   <br/>
 Turma_2017.1<br/>
  
   <br/>
  
  Universidade Estadual da Paraíba<br/>
  
  http://departamentos.uepb.edu.br/estatistica/corpo-docente/ <br/>
  
</div> 

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

#### **Modelos de Regressão**

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

#### Análise da Variância

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
