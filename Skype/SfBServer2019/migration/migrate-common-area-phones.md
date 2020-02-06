---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Les téléphones portables courants sont les téléphones IP qui se trouvent le plus souvent dans un espace de travail partagé ou une zone commune (par exemple, salle d’attente, cuisine ou étage d’usine). Il n’est pas nécessaire de connecter des téléphones communs à un ordinateur pour fournir une fonctionnalité de communications unifiées (UC) Skype entreprise Server. Après avoir migré un déploiement vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés au numéro local hérité. À l’aide de Skype entreprise Server Management Shell, vous devez tout d’abord récupérer tous les objets de contact associés aux numéros de téléphone de zone commune hérités, puis déplacer ces objets vers le pool Skype entreprise Server 2019.
ms.openlocfilehash: 5110f91788d09f644e20680f91f1cbafe146bdd6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813562"
---
# <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

Les téléphones portables courants sont les téléphones IP qui se trouvent le plus souvent dans un espace de travail partagé ou une zone commune (par exemple, salle d’attente, cuisine ou étage d’usine). Il n’est pas nécessaire de connecter des téléphones communs à un ordinateur pour fournir une fonctionnalité de communications unifiées (UC) Skype entreprise Server. Après avoir migré un déploiement vers Skype entreprise Server 2019, vous devez également migrer les objets de contact associés au numéro local hérité. À l’aide de Skype entreprise Server Management Shell, vous devez tout d’abord récupérer tous les objets de contact associés aux numéros de téléphone de zone commune hérités, puis déplacer ces objets vers le pool Skype entreprise Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

1. À partir du serveur frontal Skype entreprise Server 2019, ouvrez Skype entreprise Server Management Shell.
    
2. À partir de la ligne de commande, tapez ce qui suit :
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Pour vérifier que tous les objets de contact ont été déplacés vers le pool Skype entreprise Server 2019, à partir de Skype entreprise Server Management Shell, tapez les informations suivantes :
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Vérifiez que tous les objets de contact sont désormais associés au pool 2019 de Skype entreprise Server.
    

