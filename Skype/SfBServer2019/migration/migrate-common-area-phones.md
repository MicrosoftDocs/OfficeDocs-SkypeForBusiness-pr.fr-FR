---
title: Migration des téléphones de partie commune
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier. Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir des fonctionnalités de communications unifiées (UC) Skype Entreprise Server. Après avoir migré un déploiement vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés au téléphone de partie commune hérité. À l’aide de Skype Entreprise Server Management Shell, vous allez d’abord récupérer tous les objets contact associés aux téléphones de partie commune hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752706"
---
# <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier. Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir des fonctionnalités de communications unifiées (UC) Skype Entreprise Server. Après avoir migré un déploiement vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés au téléphone de partie commune hérité. À l’aide de Skype Entreprise Server Management Shell, vous allez d’abord récupérer tous les objets contact associés aux téléphones de partie commune hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

1. À partir du serveur frontal Skype Entreprise Server 2019, ouvrez Skype Entreprise Server Management Shell.
    
2. Sur la ligne de commande, tapez ce qui suit :
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Pour vérifier que tous les objets contact ont été déplacés vers le pool Skype Entreprise Server 2019, à partir de Skype Entreprise Server Management Shell, tapez ce qui suit :
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Vérifiez que tous les objets contact sont désormais associés au pool Skype Entreprise Server 2019.
    

