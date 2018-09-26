---
title: Réinitialisation du contrôle d’admission des appels
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer CAC hébergement à un Skype pour Business Server 2019 pool avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027318"
---
# <a name="reset-call-admission-control"></a>Réinitialisation du contrôle d’admission des appels

Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer CAC hébergement à un Skype pour Business Server 2019 pool avant de pouvoir supprimer le pool frontal hérité.
  
### <a name="to-reset-cac"></a>Pour réinitialiser CAC

1. Ouvrez le Générateur de topologie.
    
2. Cliquez sur le nœud du site, puis cliquez sur **Modifier les propriétés**.
    
3. Sous **paramètres de contrôle d’Admission des appels**, assurez-vous de **Qu'activer le contrôle d’admission des appels** est sélectionnée. 
    
4. Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le Skype pour le pool d’entreprise Server 2019 pour héberger CAC, puis cliquez sur **OK**.
    
5. Publiez la topologie.
    

