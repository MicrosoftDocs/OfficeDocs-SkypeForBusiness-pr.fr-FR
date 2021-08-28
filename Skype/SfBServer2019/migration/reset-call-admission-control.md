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
ms.localizationpriority: medium
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement cac vers un pool Skype Entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: f660f14adfcdee64d9fa4c79e08393d4f0a0af2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583448"
---
# <a name="reset-call-admission-control"></a>Réinitialisation du contrôle d’admission des appels

Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement cac vers un pool Skype Entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
  
### <a name="to-reset-cac"></a>Pour réinitialiser le service Contrôle d’admission des appels

1. Ouvrez le Générateur de topologie.
    
2. Cliquez avec le bouton droit sur le nœud du site, puis cliquez sur **Modifier les propriétés**.
    
3. Sous **Définition du contrôle d’admission des appels**, assurez-vous que l’option **Activer le contrôle d’admission des appels** est sélectionnée. 
    
4. Sous **pool frontal pour** exécuter le contrôle d’admission des appels , sélectionnez le pool Skype Entreprise Server 2019 qui doit héberger le contrôle d’admission des appels, puis cliquez sur **OK.**
    
5. Publiez la topologie.
    

