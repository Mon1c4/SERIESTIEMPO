# SERIESTIEMPO
12 02 2018
##



quantile(rpoisson)
summary (rpoisso)

#lectura de datos
#instalacion


#LA FORMA MAS FACIL DE LEER ES INSTALAR TODO EL TIDYVERSE:
install.packages("tidyverse")
install.packages("readr")
install.packages("readxl")
install.packages("haven")
install.packages("sav")
library(readr)

#read_csv():archivos delimitados por comas
#read_tsv():archivod delimitados por tabulado
#read_delim():archivos delimitados generales
#read_fwf():archivos de ancho fijo
#read_table():archivos tabulares donde las columnas estan separadas por espacios
#read_log():archivos de registro web

mtcars<-read_csv(readr_example("mtcars.csv"))
mtcars

#FORMATO CVS
library(readr)
datos_csv<-read.csv("C://Users//Sala-D26//Desktop//clase1.csv")

#FORMATO EXCEL
library(readxl)
datos_excel<-read.excel()
head(datos_excel)
tail(datos_excel)

#FORMATO SPSS
library(haven)
datos_spss<-read.sav("C://Users//Sala-D26//Desktop//ejemplo.sav")

#FORMATO STATA
library(haven)
datos_stata<-read.stata("C://Users//Sala-D26//Desktop//clase.dta")

#FORMATO SAS
library(haven)
datos_sas<-read.sas("C://Users//Sala-D26//Desktop//arima_est2.sas7bdat")

#DAROS D SITIO WEB
data2<-read.table("")
head(data2)

#
#Almacenando datos
write.csv(datos_csv,"C://Users//Sala-D26//Desktop//ST")

#datos en formato binario
install.packages("feather")
library(feather)
write_feather(datos_csv,"C://Users//Sala-D26//Desktop//ST")

##########
#MARCO DE DATOS (dataframe)
#un data frame "imita" un conjunto  de datos que tienen la estructura de una matriz,
#pero se trata de una lista cuyos elemtnos son vectyores o factores (columnas)

obs<-c(1,2,3,4,5,6,7,8,9,10)
nombre<-c("ANDRES","PAOLA","ERIKA","ARIADNA","RAFAEL","MIGUEL","MARIELA","KAREN","ANA","FERNANDO")
edad<-c(28,17,18,22,30,27,22,24,23,21)
ciudad<-c("TOL","CDMX","GDL","TOL","MTY","TOL","GDL","MEX","MEX","MTY")
ingreso<-c(2000,3000,2000,3500,2500,4000,4200,2850,2330,1970)
alumnos<-data.frame(Identificador=obs,Persona=nombre,Edad=edad,Ciudad=ciudad,Ingreso=ingreso)
alumnos
head(alumnos)
head(alumnos,n=4)

tail(alumnos)
#acceder a los datos de un data frame
#leyendo los datos como matriz
alumnos[,1]
alumnos[1,]
alumnos[1,1]
alumnos[4,]
alumnos[,"Ingreso"]
alumnos$Ingreso
alumnos[1:3]
alumnos[c(1,2)]
alumnos[alumnos$Edad>=30]

#creamos otro data frame
edocivil<-c("VIUDO","SOLTERO","SOLTERO","SOLTERO","SOLTERO","CASADO","SOLTERO","SOLTERO","CASADO","SOLTERO")
alumnos2<-data.frame(Identificador=obs,Estado=edocivil)
alumnos2
#Podemos combinar "merge" ñps dataframe
merge(alumnos,alumnos2,by="Identificador")
#ordenar el dataframe
alumnos[order(alumnos$Edad,decreasing = TRUE),]
