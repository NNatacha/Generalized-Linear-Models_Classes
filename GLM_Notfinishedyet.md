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

Apostilas correspondentes à disciplina "<span style="color: blue">**Modelos Lineares Generalizados**</span>"

[Gilberto de Paula](https://www.ime.usp.br/~giapaula/texto_2013.pdf) e [Gauss e Clarice](http://www.lce.esalq.usp.br/arquivos/aulas/2010/LCE5868/livro.pdf)

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

 Agora, verificaremos, se <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20COV%28%5Chat%5Cbeta_0%2C%5Chat%5Cbeta_1%29%3D-%5Cfrac%7B%5Csigma%5E2%5Cbar%7Bx%7D%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5E%7Bn%7D%28x_i-%5Cbar%7Bx%7D%29%5E2%7D"/>

<br/>

 Então,

<br/>

<p align="center">
<img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Cbegin%7Balign*%7D%20COV%28%5Chat%5Cbeta_0%2C%5Chat%5Cbeta_1%29%26%3DCOV%28%5Cbar%7By%7D-%5Chat%5Cbeta_%7B1%7D%5Cbar%7Bx%7D%2C%5Chat%5Cbeta_1%29%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-COV%28%5Chat%5Cbeta_1%5Cbar%7Bx%7D%2C%5Chat%5Cbeta_1%29%5Cnonumber%5C%5C%20%26%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-%5Cbar%7Bx%7DCOV%28%5Chat%5Cbeta_1%2C%5Chat%5Cbeta_1%29%5Cnonumber%5C%5C%20%26%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-%5Cbar%7Bx%7DVar%28%5Chat%5Cbeta_1%29%5Cnonumber%5C%5C%20%26%3DCOV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29-%7B%5Cfrac%7B%5Cbar%7Bx%7D%5Csigma%5E2%7D%7B%5Csum%5Climits_%7Bi%3D1%7D%5En%28x_i-%5Cbar%7Bx%7D%29%5E2%7D%7D%20%5Cend%7Balign*%7D" />
   </p>

<br/>

* **_Obs_**: A _Esperança_ e a _Variância_ de <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20%5Chat%5Cbeta_0" /> foram dadas como exercício para os discentes.

<br/>

 Agora, temos que provar que <img src="https://latex.codecogs.com/gif.latex?%5Csmall%20COV%28%5Cbar%7By%7D%2C%5Chat%5Cbeta_1%29%3D0" />:
