# femicidios

---
title: "Trabajo Curso R UBA"
author: "Marilina Santero"
date: "18/9/2019"
output: html_document
editor_options: 
  chunk_output_type: console
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

Primero cargo los paquetes que necesito

```{r}
library(tidyverse)
library(sf)
```
Voy a usar datos de verdad de *femicidios*, por provincia, desde el año 2012, publicados por el Ministerio de Justicia y Derechos Humanos. El formato original de los datos es ".csv (“comma separated values”) un formato muy popular en el mundo de la ciencia de datos, ya que es muy fácil de manipular y compartir entre sistemas.

La Unidad de Registro, Sistematización y Seguimiento de Femicidios y Homicidios Agravados por el Género del Ministerio de Justicia y Derechos Humanos registra los femicidios y homicidios agravados por el género desde el año 2012 a la fecha. La base se nutre de diversas fuentes: artículos de prensa escrita, denuncias policiales y judiciales, denuncias realizadas ante la Secretaría de Derechos Humanos. Se identifican dos tipos de femicidio, directo y vinculado. Se entiende por femicidio vinculado los homicidios cometidos en dos situaciones: cuando se asesina a personas que intentan evitar el femicidio, o a personas con vínculo afectivo con la mujer, generalmente sus hijas/os, a fin de castigarla. El registro cuenta con información desde diciembre de 2012. 


La pregunta que nos interesa responder es: __¿Cómo o cuánto es la diferencia en femicidios entre las regiones de Argentina?__
```{r}
femicidios <- read.csv('http://datos.jus.gob.ar/dataset/27bb9b2c-521b-406c-bdf9-98110ef73f34/resource/583cec9a-3022-4234-8b32-17692a267aac/download/registro-de-femicidios-20190909.csv')

dim(femicidios)

names(femicidios)

head(femicidios)



```


Voy a realizar una exploración gráfica que nos muestre a cuanto ascienden los femicidios en cada provincia durante 2012-2019:



```{r}
ggplot(femicidios) +
    geom_col(aes(x = factor(hecho_provincia), y = "" ))+
  labs(x = "Provincias",y = "Casos Femicidios") +
  theme(axis.text.x = element_text(angle = 90, hjust = 1))

```
