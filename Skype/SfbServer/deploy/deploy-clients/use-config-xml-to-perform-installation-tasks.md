---
title: Utiliser config. xml pour effectuer des tâches d’installation dans les clients Skype entreprise
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Résumé : comment utiliser le fichier Config.xml pour fournir des instructions d’installation supplémentaires.'
ms.openlocfilehash: dc7491899562e665af7d6f63470cf2fc2b904730
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290274"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Utiliser config. xml pour effectuer des tâches d’installation dans les clients Skype entreprise

**Résumé :** comment utiliser le fichier Config.xml pour fournir des instructions d’installation supplémentaires.

Même si l’outil de personnalisation Office est le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations ci-dessous ne peuvent être effectuées qu’avec le fichier Config.xml :

- Spécifiez le chemin d’accès au point d’installation réseau.

- Sélectionnez les produits à installer.

- Configurez la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels.

- Spécifiez les options d’installation, comme le nom d’utilisateur.

- Copiez la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office.

- Ajoutez ou supprimez des langues dans l’installation.

Nous vous recommandons d’utiliser le fichier config. xml pour configurer l’installation silencieuse de Skype entreprise. 

Par défaut, le fichier config. XML qui est stocké dans le dossier de produit principal (par exemple, \ _Product_). WW) envoie le programme d’installation de ce produit. Par exemple, le fichier config. xml dans le dossier suivant installe Skype entreprise:

- \\server\share\Skype15\Skype.WW \Config.xml

Le tableau suivant répertorie les éléments config. xml fréquemment utilisés pour l’installation de Skype entreprise.

**Éléments de Config.xml**


| **Élément**              | **Description**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuration  <br/>     | Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync (cela fonctionne pour les clients Skype Entreprise)  <br/>                                                                                                                                                          |
| OptionState  <br/>       | Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées lors de l’installation. Utilisez les attributs suivants pour empêcher l’installation de Business Connectivity Services, qui inclut les composants partagés qui interfèrent avec Outlook: <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Display  <br/>           | Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants : <br/>  CompletionNotice = "Yes"                                                                                                                                                                                |
| Journalisation  <br/>           | Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants : <br/>  Type = "désactivé"                                                                                                                                                                                       |
| Paramètre  <br/>           | Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :<br/>  Définition de l’ID = " *nom*" (le nom de la propriété du programme d’installation de Windows)  <br/>  Value = " *value*" (valeur à attribuer à la propriété)  <br/>                                                             |
| DistributionPoint  <br/> | Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :<br/>  Emplacement = " *path*"  <br/>                                                                                                                                     |

L’exemple suivant montre un fichier config. xml pour une installation silencieuse standard du client Skype entreprise. 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Des informations détaillées sur l’utilisation du fichier config. xml pour effectuer des tâches d’installation et de [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)maintenance d’Office sont disponibles à l’adresse.

## <a name="to-customize-the-configxml-file"></a>Pour personnaliser le fichier Config.xml

1. Ouvrez le fichier Config.xml avec un éditeur de texte, comme le Bloc-notes.

2. Recherchez les lignes qui contiennent les éléments à modifier.

3. Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser. Veillez à supprimer les séparateurs de commentaires, «\<!--» et «--\>». Par exemple, utilisez la syntaxe suivante :

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Enregistrez le fichier Config.xml.


