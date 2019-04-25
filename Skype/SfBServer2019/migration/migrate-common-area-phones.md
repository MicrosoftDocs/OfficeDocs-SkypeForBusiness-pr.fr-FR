---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Téléphones de partie commune sont IP téléphones que plus souvent se trouvent dans un espace de travail partagé ou la partie commune, comme un atelier de salle d’attente, cuisine ou usine. Téléphones de partie commune est inutile d’être connecté à un ordinateur pour fournir que Skype pour Business Server unifiée la fonctionnalité de communications (UC). Après la migration d’un déploiement à Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec le téléphone en zone commune hérité. À l’aide de Skype pour Business Server Management Shell vous serez tout d’abord récupérer tous les objets contact associés aux anciens téléphones en zone commune, puis déplacer ces objets vers le Skype pour Business Server 2019 pool.
ms.openlocfilehash: d17e15224a9124eaf3e9fd6696e6ecd9265044eb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231664"
---
# <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

Téléphones de partie commune sont IP téléphones que plus souvent se trouvent dans un espace de travail partagé ou la partie commune, comme un atelier de salle d’attente, cuisine ou usine. Téléphones de partie commune est inutile d’être connecté à un ordinateur pour fournir que Skype pour Business Server unifiée la fonctionnalité de communications (UC). Après la migration d’un déploiement à Skype pour Business Server 2019, vous devez également migrer les objets contact associés avec le téléphone en zone commune hérité. À l’aide de Skype pour Business Server Management Shell, vous tout d’abord récupérer tous les objets contact associés aux anciens téléphones en zone commune et puis déplacer ces objets vers le Skype pour Business Server 2019 pool.
  
### <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

1. Skype pour le serveur frontal Business Server 2019, ouvrez Skype pour Business Server Management Shell.
    
2. À partir de la ligne de commande, tapez ce qui suit :
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Pour vérifier que tous les objets contact ont été déplacés vers le Skype pour le pool d’entreprise Server 2019, à partir de la Skype pour Business Server Management Shell tapez ce qui suit :
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Vérifiez que tous les objets contact sont désormais associé à la Skype pour Business Server 2019 pool.
    

