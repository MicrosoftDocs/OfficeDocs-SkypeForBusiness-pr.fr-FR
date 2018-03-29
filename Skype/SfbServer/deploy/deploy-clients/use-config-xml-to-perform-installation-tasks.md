---
title: Utilisation du fichier Config.xml pour effectuer les tâches d’installation dans Skype Entreprise Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Résumé : Comment faire pour utiliser le fichier Config.xml pour spécifier des instructions d’installation supplémentaires.'
ms.openlocfilehash: f55683d672df890be8baf0ac7ca50b3170faf3d2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-server-2015"></a>Utilisation du fichier Config.xml pour effectuer les tâches d’installation dans Skype Entreprise Server 2015
 
**Résumé :** comment utiliser le fichier Config.xml pour fournir des instructions d’installation supplémentaires.
  
Même si l’outil de personnalisation Office est le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations ci-dessous ne peuvent être effectuées qu’avec le fichier Config.xml :
  
- Spécifiez le chemin d’accès au point d’installation réseau.
    
- Sélectionnez les produits à installer.
    
- Configurez la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels.
    
- Spécifiez les options d’installation, comme le nom d’utilisateur.
    
- Copiez la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office.
    
- Ajoutez ou supprimez des langues dans l’installation.
    
Nous vous recommandons d’utiliser le fichier Config.xml pour configurer Skype pour une installation en mode silencieux d’entreprise. 
  
Par défaut, le fichier Config.xml stocké dans le dossier principal du produit (par exemple, \ _produit_. WW) indique au programme d’installation de ce produit. Par exemple, le fichier Config.xml dans le dossier suivant installe Skype pour les entreprises :
  
- \\server\share\Skype15\Skype.WW \Config.xml
    
Les éléments Config.xml plus couramment utilisés pour Skype pour l’installation de l’entreprise sont répertoriés dans le tableau suivant.
  
**Éléments config.Xml**

|**Élément**|**Description**|
|:-----|:-----|
|Configuration  <br/> |Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync (cela fonctionne pour les clients Skype Entreprise)  <br/> |
|OptionState  <br/> | Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées lors de l’installation. Pour empêcher l’installation des Services Business Connectivity, qui inclut des composants partagés qui interfèrent avec Outlook 2016, utilisez les attributs suivants : <br/>  ID = « LOBiMain » <br/>  State="Absent" <br/>  Children="Force" <br/> |
|Display  <br/> | Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants : <br/>  CompletionNotice = « Yes » | No"(default) « <br/>  AcceptEula = « Yes » | No"(default) « <br/> |
|Journalisation  <br/> | Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants : <br/>  Type = « Off » | Standard"(default) « | « Verbose » <br/>  Modèle = » _nom de fichier_.txt » (le nom du fichier journal)  <br/> |
|Paramètre  <br/> | Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :<br/>  Définition des Id = » _nom_"(le nom de la propriété de Windows Installer)  <br/>  Valeur = » _valeur_"(la valeur à assigner à la propriété)  <br/> |
|DistributionPoint  <br/> | Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :<br/>  Emplacement = » _chemin d’accès_"  <br/> |
   
L’exemple suivant montre un fichier Config.xml pour une installation par défaut silencieuse de Skype pour les entreprises. 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Des informations détaillées sur l’utilisation du fichier Config.xml pour effectuer des tâches d’installation et de maintenance d’Office sont disponibles à l’adresse [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).
  
## <a name="to-customize-the-configxml-file"></a>Pour personnaliser le fichier Config.xml

1. Ouvrez le fichier Config.xml avec un éditeur de texte, comme le Bloc-notes.
    
2. Recherchez les lignes qui contiennent les éléments à modifier.
    
3. Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser. Assurez-vous que vous supprimez les délimiteurs de commentaire, «\<!-- » et «--\>». Par exemple, utilisez la syntaxe suivante :
    
  ```
  < DistributionPoint Location="\\server\share\Skype15" />
  ```

4. Enregistrez le fichier Config.xml.
    

