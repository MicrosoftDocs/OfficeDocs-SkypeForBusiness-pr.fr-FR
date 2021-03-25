---
title: Utiliser Config.xml pour effectuer des tâches d’installation dans les clients Skype Entreprise
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Résumé : Comment utiliser le fichier Config.xml pour spécifier des instructions d’installation supplémentaires.'
ms.openlocfilehash: dbf4c4ba4e652f4b777e0c901fee4ffb0ad68af3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121138"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Utiliser Config.xml pour effectuer des tâches d’installation dans les clients Skype Entreprise

**Résumé :** Utilisation du fichier Config.xml pour spécifier des instructions d’installation supplémentaires.

Bien que l’outil de personnalisation Office soit le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations suivantes ne peuvent être effectuées qu’avec le fichier Config.xml :

- spécifier le chemin d’accès au point d’installation réseau ;

- sélectionner les produits à installer ;

- configurer la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels ;

- spécifier les options d’installation telles que le nom de l’utilisateur ;

- copier la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office ;

- ajouter ou supprimer des langues de l’installation.

Nous vous recommandons d’utiliser le fichier Config.xml pour configurer l’installation silencieuse de Skype Entreprise. 

Par défaut, le fichier Config.xml qui est stocké dans le dossier principal du produit (par exemple, \ _produit_. WW) dirige le programme d’installation pour installer ce produit. Par exemple, le Config.xml dans le dossier suivant installe Skype Entreprise :

- \\server\share\Skype15\Skype.WW \Config.xml

Les Config.xml les plus couramment utilisés pour l’installation de Skype Entreprise sont répertoriés dans le tableau suivant.

**Éléments de Config.xml**


| **Élément**              | **Description**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuration  <br/>     | Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync (cela fonctionne pour les clients Skype Entreprise)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées pendant l’installation. Utilisez les attributs suivants pour empêcher l’installation de Services Business Connectivity, qui inclut des composants partagés qui interfèrent avec Outlook : <br/>  Id="LOBiMain » <br/>  State="Absent » <br/>  Children="Force » <br/> |
| Afficher  <br/>           | Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants : <br/>  CompletionNotice="Yes »                                                                                                                                                                                |
| Logging  <br/>           | Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants : <br/>  Type ="Off »                                                                                                                                                                                       |
| Paramètres  <br/>           | Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :<br/>  Setting Id= » *name*" (nom de la propriété Windows Installer)  <br/>  Value= » *value*" (valeur à affecter à la propriété)  <br/>                                                             |
| DistributionPoint  <br/> | Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :<br/>  Location= » *path*»  <br/>                                                                                                                                     |

L’exemple suivant montre un fichier Config.xml pour une installation silencieuse classique du client Skype Entreprise. 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Des informations détaillées sur l’utilisation du fichier Config.xml pour effectuer les tâches d’installation et de maintenance d’Office sont disponibles sur [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) .

## <a name="to-customize-the-configxml-file"></a>Pour personnaliser le fichier Config.xml

1. Ouvrez le fichier Config.xml avec un éditeur de texte, tel que le Bloc-notes.

2. Recherchez les lignes qui contiennent les éléments que vous voulez changer.

3. Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser. Veillez à supprimer les délimiteur de commentaires « \<!--" and "--\> ». Par exemple, utilisez la syntaxe suivante :

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Enregistrez le fichier Config.xml.