# Voorbeeld van (o.a.) constructor chaining
  
In de starterscode zit reeds 1 WPF project : Prb.ConstructorChaining.Wpf    
Voeg een class library toe aan de solution : Prb.ConstructorChaining.Core    
Voeg aan deze class library 1 klasse toe met de naam **EarthCalculations**   
Deze klasse beschikt over volgende publieke velden (of eigenschappen) :  
  * int **earthRadius** (in geval van eigenschappen : read only) = de straal van de aarde  
    Aan dit veld (of eigenschap) kennen we de standaardwaarde 6371 toe.
  * double **earthCircumference** (in geval van eigenschappen : read only) = de omtrek van de aarde    
  * double **earthSurface** (in geval van eigenschappen : read only)  = de oppervlakte van de aarde  
  * double **regionSurface** = de oppervlakte van een gegeven regio  
  
De klasse voorziet 1 methode met de naam **PercentageOfEarth**  
  * de methode retourneert een double waarde  
  * de methode rekent uit hoeveel percent de **regionSurface** uitmaakt van de totale oppervlakte van de aarde (**earthSurface**)    

> oppervlakte van een bol : 4 * Pi * straal² 
  
De klasse heeft 2 constructors :   
  * constroctor zonder argumenten    
    in deze constructor wordt **earthCircomference** en **earthSurface** berekent en gevuld (op basis van **earthRadius**)     
  * constructor met 1 argument : de waarde van **regionSurface**  
    deze constructor laat eerst de berekeningen van de argumentloze constructor uitvoeren   
    deze constructor vult het veld/eigenschap   **regionSurface**

In je WPF ga je de waarde uit txtArea gaan uitlezen (bv in de variabele area), wanneer op btnReport wordt geklikt.  
Vervolgens maak je een object aan van het type **EarthCalculations**.  
Je moet dit op 2 manieren kunnen doen :   
  * EarthCalculations earthCalculations = new EarthCalculations();  
    earthCalculations.regionSurface = area;  
  * EarthCalculations earthCalculations = new EarthCalculations(area);  

Met behulp van dit object vul je tenslotte tblReport met volgende info :    

> Straal van de aarde = 6371 km  
> Omtrek van de aarde = ... km  
> Oppervlakte van de aarde = ... km²  
> Oppervlakte van de opgegeven regio = ... km²  
> De opgegeven regio beslaat ... % van de totale aardoppervlakte   
