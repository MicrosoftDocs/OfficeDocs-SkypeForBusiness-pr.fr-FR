---
title: Réinitialisation du contrôle d’admission des appels
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
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753296"
---
# <a name="reset-call-admission-control"></a>Réinitialisation du contrôle d’admission des appels

Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
  
### <a name="to-reset-cac"></a>Pour réinitialiser le service Contrôle d’admission des appels

1. Ouvrez le Générateur de topologie.
    
2. Cliquez avec le bouton droit sur le nœud du site, puis cliquez sur **Modifier les propriétés**.
    
3. Sous **Définition du contrôle d’admission des appels**, assurez-vous que l’option **Activer le contrôle d’admission des appels** est sélectionnée. 
    
4. Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le pool Skype entreprise Server 2019 qui doit héberger le contrôle d’admission des appels, puis cliquez sur **OK**.
    
5. Publiez la topologie.
    

