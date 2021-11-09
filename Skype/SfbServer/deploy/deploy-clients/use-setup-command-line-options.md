---
title: Utiliser les options de ligne de commande du programme d’installation Skype Entreprise clients
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Résumé : Découvrez les Setup.exe de ligne de commande dans Office configuration.'
ms.openlocfilehash: 6a64ac821019f49f8cbb4988ad0e42da0363245b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850478"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a>Utiliser les options de ligne de commande du programme d’installation Skype Entreprise clients
 
**Résumé :** Découvrez les Setup.exe de ligne de commande dans Office configuration.
  
La Setup.exe de commande est utilisée pour très peu d’opérations dans Office configuration. Au lieu d’utiliser les options de ligne de commande du programme d’installation, vous utilisez généralement l’outil de personnalisation Office et le fichier Config.xml pour la configuration du produit et la personnalisation des fonctionnalités.
  
La Office Setup.exe de commande reconnaît les options de ligne de commande décrites dans le tableau suivant.
  
**Office Options d'Command-Line du programme d’installation**

|**Option dCommand-Line de configuration**|**Description**|
|:-----|:-----|
|/admin  <br/> |Exécute l’Outil de personnalisation Office pour créer un fichier de personnalisation de l’installation (fichier .msp).  <br/> |
|/adminfile [chemin]  <br/> |Applique le fichier de personnalisation de l’installation spécifié à l’installation. Vous pouvez spécifier un chemin d’accès à un fichier de personnalisation spécifique (fichier .msp) ou au dossier dans lequel vous stockez les fichiers de personnalisation.  <br/> |
|/config [chemin]  <br/> |Spécifie le fichier Config.xml que le programme d’installation utilise au cours de l’installation. Utilisez l’option /config pour spécifier le fichier Config.xml personnalisé pour Skype Entreprise installations, par exemple :`/config \\server\share\Skype15\Skype.WW\Config.xml` <br/> |
|/modify Skype  <br/> |Utilisée avec un fichier Config.xml modifié, cette option permet d’exécuter le programme d’installation en mode maintenance et d’apporter des modifications à une installation Office existante. Par exemple, vous pouvez utiliser l’option /modify pour ajouter ou supprimer Skype Entreprise fonctionnalités.  <br/> |
|/repair Skype  <br/> |Exécute le programme d’installation à partir de l’ordinateur de l’utilisateur pour réparer Skype Entreprise.  <br/> |
|/uninstall Skype  <br/> |Exécute le programme d’installation pour Skype Entreprise’ordinateur de l’utilisateur.  <br/> |
   


