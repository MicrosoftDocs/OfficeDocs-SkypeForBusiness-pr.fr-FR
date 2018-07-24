---
title: Utilisez les options de ligne de commande du programme d’installation avec Skype pour les clients d’entreprise
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé : Découvrez les opérations de ligne de commande Setup.exe dans le programme d’installation Office.'
ms.openlocfilehash: 13005f96b353b8648ed676ef68af54b76a99e48c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974451"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Utilisez les options de ligne de commande du programme d’installation avec Skype pour les clients d’entreprise
 
**Résumé :** Découvrez les opérations de ligne de commande Setup.exe dans le programme d’installation Office.
  
La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office. Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous allez généralement utiliser l’outil de personnalisation Office et le fichier Config.xml pour la personnalisation du programme d’installation et de la fonctionnalité de produit.
  
La ligne de commande de Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.
  
**Options de ligne de commande du programme d’installation Office**

|**Options de ligne de commande du programme d’installation**|**Description**|
|:-----|:-----|
|/admin  <br/> |Exécute l’outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).  <br/> |
|/adminfile [chemin]  <br/> |Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.  <br/> |
|/config [chemin]  <br/> |Spécifie le fichier Config.xml utilisé par le programme d’installation lors de l’installation. Utilisez l’option /config pour spécifier le fichier Config.xml que vous avez personnalisé pour Skype pour les installations d’entreprise, par exemple :`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante. Par exemple, vous pouvez utiliser l’option pour ajouter ou supprimer des Skype pour les fonctionnalités d’entreprise / modify.  <br/> |
|/repair Skype  <br/> |Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype pour les entreprises.  <br/> |
|/uninstall Skype  <br/> |Exécute le programme d’installation pour supprimer Skype pour les entreprises à partir de l’ordinateur de l’utilisateur.  <br/> |
   


