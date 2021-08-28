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
ms.localizationpriority: medium
description: Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier. Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir Skype Entreprise Server de communications unifiées (UC). Après avoir migré un déploiement vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés à l’Téléphone. À l’aide de Skype Entreprise Server Management Shell, vous allez d’abord récupérer tous les objets contact associés aux téléphones de partie commune hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.
ms.openlocfilehash: dabb91925b2d5271ba2760f62dd962ed7fa7a24c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579528"
---
# <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

Les téléphones de partie commune sont des téléphones IP se trouvant la plupart du temps dans un espace de travail partagé ou une partie commune, comme un lobby, une cuisine ou un atelier. Les téléphones de partie commune n’ont pas besoin d’être connectés à un ordinateur pour fournir Skype Entreprise Server de communications unifiées (UC). Après avoir migré un déploiement vers Skype Entreprise Server 2019, vous devez également migrer les objets contact associés à l’Téléphone. À l’aide de Skype Entreprise Server Management Shell, vous allez d’abord récupérer tous les objets contact associés aux téléphones de partie commune hérités, puis déplacer ces objets vers le pool Skype Entreprise Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migration des téléphones de partie commune

1. À partir Skype Entreprise Server serveur frontal 2019, ouvrez Skype Entreprise Server Management Shell.
    
2. Sur la ligne de commande, tapez ce qui suit :
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Pour vérifier que tous les objets contact ont été déplacés vers le pool Skype Entreprise Server 2019, à partir de Skype Entreprise Server Management Shell, tapez ce qui suit :
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Vérifiez que tous les objets contact sont désormais associés au pool Skype Entreprise Server 2019.
    

