---
title: Utiliser les options de la ligne de commande du programme d’installation avec les clients Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé: Découvrez les opérations de ligne de commande Setup. exe dans le programme d’installation d’Office.'
ms.openlocfilehash: a84c1f8a69bdff07dfec5e274932a522bf139c9a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234834"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Utiliser les options de la ligne de commande du programme d’installation avec les clients Skype entreprise
 
**Résumé:** En savoir plus sur les opérations de ligne de commande Setup. exe dans le programme d’installation d’Office.
  
La ligne de commande Setup.exe est utilisée pour très peu d’opérations dans le programme d’installation d’Office. Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous utiliserez généralement l’outil de personnalisation Office et le fichier config. xml pour la configuration du produit et la personnalisation des fonctionnalités.
  
La ligne de commande de Setup.exe reconnaît les options de ligne de commande décrites dans le tableau suivant.
  
**Options de ligne de commande du programme d’installation Office**

|**Options de ligne de commande du programme d’installation**|**Description**|
|:-----|:-----|
|/admin  <br/> |Exécute l’outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).  <br/> |
|/adminfile [chemin]  <br/> |Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.  <br/> |
|/config [chemin]  <br/> |Spécifie le fichier Config.xml utilisé par le programme d’installation lors de l’installation. Utilisez l’option/config pour spécifier le fichier config. XML que vous avez personnalisé pour les installations Skype entreprise, par exemple:`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante. Par exemple, vous pouvez utiliser l’option/Modify pour ajouter ou supprimer des fonctionnalités Skype entreprise.  <br/> |
|/repair Skype  <br/> |Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype entreprise.  <br/> |
|/uninstall Skype  <br/> |Exécute le programme d’installation pour supprimer Skype entreprise de l’ordinateur de l’utilisateur.  <br/> |
   


