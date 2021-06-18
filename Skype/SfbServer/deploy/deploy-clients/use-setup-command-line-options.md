---
title: Utiliser les options de ligne de commande du programme d’installation avec les clients Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé : Découvrez les Setup.exe de ligne de commande dans le programme d’installation d’Office.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837204"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Utiliser les options de ligne de commande du programme d’installation avec les clients Skype Entreprise
 
**Résumé :** Découvrez les Setup.exe de ligne de commande dans le programme d’installation d’Office.
  
La Setup.exe de commande est utilisée pour très peu d’opérations dans le programme d’installation d’Office. Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous utilisez généralement l’outil de personnalisation Office et le fichier Config.xml pour la configuration du produit et la personnalisation des fonctionnalités.
  
La ligne de Setup.exe Office reconnaît les options de ligne de commande décrites dans le tableau suivant.
  
**Options d’installation Command-Line Office**

|**Option dCommand-Line de configuration**|**Description**|
|:-----|:-----|
|/admin  <br/> |Exécute l’Outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).  <br/> |
|/adminfile [chemin]  <br/> |Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.  <br/> |
|/config [chemin]  <br/> |Spécifie le fichier Config.xml que le programme d’installation utilise au cours de l’installation. Utilisez l’option /config pour spécifier le fichier Config.xml personnalisé pour les installations de Skype Entreprise, par exemple :  `/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante. Par exemple, vous pouvez utiliser l’option /modify pour ajouter ou supprimer des fonctionnalités Skype Entreprise.  <br/> |
|/repair Skype  <br/> |Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype Entreprise.  <br/> |
|/uninstall Skype  <br/> |Exécute le programme d’installation pour supprimer Skype Entreprise de l’ordinateur de l’utilisateur.  <br/> |
   


