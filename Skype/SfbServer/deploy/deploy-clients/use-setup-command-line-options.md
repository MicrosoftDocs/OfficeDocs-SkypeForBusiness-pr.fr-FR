---
title: Utilisation des options de ligne de commande du programme d’installation dans Skype Entreprise Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé : Découvrez les opérations de ligne de commande Setup.exe dans le programme d’installation Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a>Utilisation des options de ligne de commande du programme d’installation dans Skype Entreprise Server 2015
 
**Résumé :** Obtenir des informations sur les opérations de ligne de commande Setup.exe dans le programme d’installation Office.
  
La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office. Au lieu d’utiliser les options de ligne de commande d’installation, vous allez généralement utiliser l’outil de personnalisation Office et le fichier Config.xml pour le programme d’installation et de la fonctionnalité de personnalisation des produits.
  
La ligne de commande de Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.
  
**Options de ligne de commande d’installation de Office**

|**Option de ligne de commande du programme d’installation**|**Description**|
|:-----|:-----|
|/admin  <br/> |Exécute l’outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).  <br/> |
|/adminfile [chemin]  <br/> |Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.  <br/> |
|/config [chemin]  <br/> |Spécifie le fichier Config.xml utilisé par le programme d’installation lors de l’installation. Utilisez l’option /config pour spécifier le fichier Config.xml que vous avez personnalisé pour Skype pour les installations de l’entreprise, par exemple :`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante. Par exemple, vous pouvez utiliser le / modifier l’option pour ajouter ou supprimer des Skype pour les fonctionnalités d’entreprise.  <br/> |
|/repair Skype  <br/> |Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype pour les entreprises.  <br/> |
|/uninstall Skype  <br/> |Exécute le programme d’installation pour supprimer Skype pour les entreprises à partir de l’ordinateur de l’utilisateur.  <br/> |
   
Pour plus d’informations sur les options de ligne de commande d’installation, voir [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515). 
  

