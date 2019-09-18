# femicidios

---
title: "Trabajo Curso R UBA"
author: "Marilina Santero"
date: "18/9/2019"
output: html_document
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
