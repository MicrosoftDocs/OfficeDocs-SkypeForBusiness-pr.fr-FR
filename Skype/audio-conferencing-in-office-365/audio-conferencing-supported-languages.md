---
title: "Services d'audioconférence langues prises en charge"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 572ca0c8-b9f0-4948-9409-e12ee0b94aa0
description: "Find the dial-in conferencing language for each country or region and the culture ID assigned (en-US, da-DK, de-DE, etc)"
---

# Services d'audioconférence langues prises en charge

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](572ca0c8-b9f0-4948-9409-e12ee0b94aa0.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/572ca0c8-b9f0-4948-9409-e12ee0b94aa0). 
  
Lorsque vous la configuration et configurez audioconférence dans Office 365, vous pouvez sélectionner les principales et secondaires (4) langues qui sont utilisés lorsque les appelants se connecter à un Skype entreprise ou Microsoft Teams réunion. Voici la liste des langues prises en charge pour les conférences Audio :
  
> [!IMPORTANT]
> Langues principaux et secondaires peuvent être modifiées uniquement sur les numéros de téléphone de conférence Audio dédiés. 
  
## Langues actuellement prises en charge

|****Langue****|****Pays/Région****|****ID de culture****|
|:-----|:-----|:-----|
|Arabe  <br/> |Arabie saoudite  <br/> |ar-SA  <br/> |
|Bulgare  <br/> |Bulgarie  <br/> |bg-BG  <br/> |
|Cantonais  <br/> |Hong Kong  <br/> |zh-HK  <br/> |
|Chinois (simplifié)  <br/> |Chine  <br/> |zh-CN  <br/> |
|Chinois (traditionnel)  <br/> |Taïwan  <br/> |zh-TW  <br/> |
|Croate  <br/> |Croatie  <br/> |hr-HR  <br/> |
|Tchèque  <br/> |République tchèque  <br/> |cs-CZ  <br/> |
|Danois  <br/> |Danemark  <br/> |da-DK  <br/> |
|Néerlandais  <br/> |Pays-Bas  <br/> |nl-NL  <br/> |
|Anglais  <br/> |Australie  <br/> |en-AU  <br/> |
|Anglais  <br/> |Royaume-Uni  <br/> |en-GB  <br/> |
|Anglais  <br/> |États-Unis  <br/> |en-US  <br/> |
|Estonien  <br/> |Estonie  <br/> |et-EE  <br/> |
|Filipino  <br/> |Philippines  <br/> |fil-PH  <br/> |
|Finnois  <br/> |Finlande  <br/> |fi-FL  <br/> |
|Français  <br/> |Canada  <br/> |fr-CA  <br/> |
|Français  <br/> |France  <br/> |fr-FR  <br/> |
|Allemand  <br/> |Allemagne  <br/> |de-DE  <br/> |
|Géorgien  <br/> |Géorgie  <br/> |ka-GE  <br/> |
|Grec  <br/> |Grèce  <br/> |el-GR  <br/> |
|Hébreu  <br/> | Israël <br/> | he-IL <br/> |
|Hindi  <br/> |Inde  <br/> |hi-IN  <br/> |
|Hongrois  <br/> |Hongrie  <br/> |hu-HU  <br/> |
|Indonésien  <br/> |Indonésie  <br/> |id-ID  <br/> |
|Italien  <br/> |Italie  <br/> | it-IT <br/> |
|Japonais  <br/> |Japon  <br/> |ja-JP  <br/> |
|Coréen  <br/> |Corée  <br/> |ko-KR  <br/> |
|Letton  <br/> |Lettonie  <br/> |lv-LV  <br/> |
|Lituanien  <br/> |Lituanie  <br/> |lt-LT  <br/> |
|Malais  <br/> |Malaisie  <br/> |ms-MY  <br/> |
|Norvégien (Bokmål)  <br/> |Norvège  <br/> |nb-NO  <br/> |
|Polonais  <br/> |Pologne  <br/> |pl-PL  <br/> |
|Portugais  <br/> |Brésil  <br/> |pt-BR  <br/> |
|Portugais  <br/> |Portugal  <br/> |pt-PT  <br/> |
|Roumain  <br/> |Roumanie  <br/> |ro-RO  <br/> |
|Russe  <br/> |Russie  <br/> |ru-RU  <br/> |
|Slovaque  <br/> |Slovaquie  <br/> |sk-SK  <br/> |
|Slovène  <br/> |Slovénie  <br/> |sk-SK  <br/> |
|Espagnol  <br/> |Mexique  <br/> |es-MX  <br/> |
|Espagnol  <br/> |Espagne  <br/> |es-ES  <br/> |
|Suédois  <br/> |Suède  <br/> |sv-SE  <br/> |
|Thaï  <br/> |Thaïlande  <br/> |th-TH  <br/> |
|Turc  <br/> |Turquie  <br/> |tr-TR  <br/> |
|Ukrainien  <br/> |Ukraine  <br/> |uk-UA  <br/> |
   
Si vous recherchez des pays ou régions où vous pouvez acheter des services de conférence Audio, voir [La conférence RTC avec numéros de téléphone est-elle disponible dans mon pays ou ma région ?](https://support.office.com/article/1096d81e-7e14-488c-95d8-b8322e39c059).
  
Si vous cherchez à certains pays ou régions qui contiennent des numéros de téléphone pour les conférences Audio, voir [Numéros de téléphone pour les conférences Audio](phone-numbers-for-audio-conferencing.md).
  
## Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser les applets de commande [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) ou[Set-Csonlinedialinconferencingservicenumberhttp://go.Microsoft.com/fwlink/?LinkId=617689](https://go.microsoft.com/fwlink/?LinkId=617689) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Pourquoi vous devez utiliser Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages dans vitesse, simplicité et la productivité sur qu'à l'aide du centre d'administration Office 365, tels que lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. En savoir plus sur les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). 
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  
## Voir aussi
<a name="MT_Footer"> </a>

#### 

[Conférence rendez-vous dans Office 365](../misctopics/dial-in-conferencing-in-office-365.md)

