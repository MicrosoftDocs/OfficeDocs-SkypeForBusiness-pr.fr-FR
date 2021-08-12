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
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement cac vers un pool Skype Entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: c3ebb748d877e88060b699b1599c39038124565df361c5032533260e4c5643e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334566"
---
# <a name="reset-call-admission-control"></a>Réinitialisation du contrôle d’admission des appels

Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement cac vers un pool Skype Entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
  
### <a name="to-reset-cac"></a>Pour réinitialiser le service Contrôle d’admission des appels

1. Ouvrez le Générateur de topologie.
    
2. Cliquez avec le bouton droit sur le nœud du site, puis cliquez sur **Modifier les propriétés**.
    
3. Sous **Définition du contrôle d’admission des appels**, assurez-vous que l’option **Activer le contrôle d’admission des appels** est sélectionnée. 
    
4. Sous **pool frontal pour** exécuter le contrôle d’admission des appels , sélectionnez le pool Skype Entreprise Server 2019 qui doit héberger le contrôle d’admission des appels, puis cliquez sur **OK.**
    
5. Publiez la topologie.
    

