---
layout: post
title:  Filtra columnas con list comprehensions
date:   2023-12-22 18:40:16
description: Usa list comprehension para filtrar columnas de un dataset
tags: python 
category:  programación 
---

Este es el problema, tienes las columnas de tu dataframe, y quieres filtrar solo las que dicen `"Electricity Rate"`, estas segurx que dice eso, pero no recuerdas si está en mayúsculas, minúsculas... 
```
columnas = ['BATH_LIGHT:Lights Electricity Rate (W)',
       'B_1:Space People Occupant Count ()', 'Ti_B_1',
       'C:Space People Occupant Count ()', 'Ti_C',
       'COCINA:Infiltration Air Change Rate (ach)',
       'COCINA_ESTUFA_EQUIPMENT:Electric Equipment Electricity Rate (W)',
       'COCINA_REFR_EQUIPMENT:Electric Equipment Electricity Rate (W)', 'Ti_E',
       'ESTANCIA_COCINA_LIGHT:Lights Electricity Rate (W)',
       'ESTANCIA_TV_EQUIPMENT:Electric Equipment Electricity Rate (W)', 'To',
       'R_1:Space People Occupant Count ()', 'Ti_R_1',
       'R_1_LIGHT:Lights Electricity Rate (W)',
       'R_2:Space People Occupant Count ()', 'Ti_R_2',
       'R_2_LIGHT:Lights Electricity Rate (W)',
       'STAND_BY_EQUIPMENT:Electric Equipment Electricity Rate (W)'],
      dtype='object', name='variable_name')
```
Te acuerdas de tu curso [Python de cero a usuario](https://www.coursera.org/learn/python-usuario) del manejo de `list comprehension` y del uso de `strings` que puedes hacer lo siguiente:
```
electricidad = [columna for columna in columnas if 'electricity rate' in columna.lower()]
```
y entonces obtienes:
```
['BATH_LIGHT:Lights Electricity Rate (W)',
 'COCINA_ESTUFA_EQUIPMENT:Electric Equipment Electricity Rate (W)',
 'COCINA_REFR_EQUIPMENT:Electric Equipment Electricity Rate (W)',
 'ESTANCIA_COCINA_LIGHT:Lights Electricity Rate (W)',
 'ESTANCIA_TV_EQUIPMENT:Electric Equipment Electricity Rate (W)',
 'R_1_LIGHT:Lights Electricity Rate (W)',
 'R_2_LIGHT:Lights Electricity Rate (W)',
 'STAND_BY_EQUIPMENT:Electric Equipment Electricity Rate (W)']
```

Lo que hiciste fue iterar cada elemento de `columnas` y convertirlo a minúsculas (`columna.lower()`), entonces ahí verificas que `electricity rate` existe en `columna` y le permites el paso, filtrando los elementos que coinciden con tu.

Muy zen, ¿o no?