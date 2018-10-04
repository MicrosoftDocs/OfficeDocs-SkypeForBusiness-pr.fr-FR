---
title: Utiliser Config.xml pour effectuer des tâches d’installation dans Skype pour les clients d’entreprise
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Résumé : comment utiliser le fichier Config.xml pour fournir des instructions d’installation supplémentaires.'
ms.openlocfilehash: a6234424240dc0d7ebb70762598467bfcee997e2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371512"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>Utiliser Config.xml pour effectuer des tâches d’installation dans Skype pour les clients d’entreprise

**Résumé :** comment utiliser le fichier Config.xml pour fournir des instructions d’installation supplémentaires.

Même si l’outil de personnalisation Office est le principal outil pour l’installation personnalisée, les administrateurs peuvent utiliser le fichier Config.xml pour spécifier des instructions d’installation non disponibles dans cet outil. Les personnalisations ci-dessous ne peuvent être effectuées qu’avec le fichier Config.xml :

- Spécifiez le chemin d’accès au point d’installation réseau.

- Sélectionnez les produits à installer.

- Configurez la journalisation et l’emplacement du fichier de personnalisation de l’installation et les mises à jour des logiciels.

- Spécifiez les options d’installation, comme le nom d’utilisateur.

- Copiez la source d’installation locale sur l’ordinateur de l’utilisateur sans installer Office.

- Ajoutez ou supprimez des langues dans l’installation.

Nous vous recommandons d’utiliser le fichier Config.xml pour configurer Skype pour une installation en mode silencieux Business. 

Par défaut, le fichier Config.xml qui est stocké dans le dossier principal du produit (par exemple, \ _produit_. WW) dirige le programme d’installation pour installer ce produit. Par exemple, le fichier Config.xml dans le dossier suivant installe Skype pour les entreprises :

- \\server\share\Skype15\Skype.WW \Config.xml

Les éléments de Config.xml plus couramment utilisées pour Skype pour l’installation de l’entreprise sont répertoriés dans le tableau suivant.

**Éléments de Config.xml**


| **Élément**              | **Description**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Configuration  <br/>     | Élément de niveau supérieur (obligatoire). Contient l’attribut Product, par exemple : Product=Lync (cela fonctionne pour les clients Skype Entreprise)  <br/>                                                                                                                                                          |
| Élément OptionState  <br/>       | Spécifie la façon dont des fonctionnalités de produits spécifiques sont gérées lors de l’installation. Pour empêcher l’installation de Business Connectivity Services, qui inclut des composants partagés interféreront avec Outlook, utilisez les attributs suivants : <br/>  ID = « LOBiMain » <br/>  State="Absent" <br/>  Children="Force" <br/> |
| Display  <br/>           | Niveau d’interface utilisateur affiché pour l’utilisateur par le programme d’installation. Les attributs type sont les suivants : <br/>  CompletionNotice = « Yes »                                                                                                                                                                                |
| Journalisation  <br/>           | Options déterminant le type de journalisation mis en œuvre par le programme d’installation. Les attributs types sont les suivants : <br/>  Type = « Off »                                                                                                                                                                                       |
| Paramètre  <br/>           | Spécifie les valeurs des propriétés de Windows Installer. Les attributs type sont les suivants :<br/>  Setting Id = « *nom*» (le nom de la propriété Windows Installer)  <br/>  Valeur = » *valeur*"(valeur à attribuer à la propriété)  <br/>                                                             |
| DistributionPoint  <br/> | Chemin d’accès complet du point d’installation réseau à partir duquel l’installation doit s’exécuter. Comprend l’attribut Location :<br/>  Emplacement = » *chemin d’accès*»  <br/>                                                                                                                                     |

L’exemple suivant montre un fichier Config.xml pour une installation sans assistance de le Skype pour client d’entreprise. 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

Des informations détaillées sur l’utilisation du fichier Config.xml pour effectuer des tâches d’installation et de maintenance Office sont disponibles à l’adresse [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).

## <a name="to-customize-the-configxml-file"></a>Pour personnaliser le fichier Config.xml

1. Ouvrez le fichier Config.xml avec un éditeur de texte, comme le Bloc-notes.

2. Recherchez les lignes qui contiennent les éléments à modifier.

3. Modifiez l’entrée de l’élément avec les options automatisées que vous voulez utiliser. Assurez-vous que vous supprimez les délimiteurs de commentaire, «\<!-- » et «--\>». Par exemple, utilisez la syntaxe suivante :

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. Enregistrez le fichier Config.xml.


