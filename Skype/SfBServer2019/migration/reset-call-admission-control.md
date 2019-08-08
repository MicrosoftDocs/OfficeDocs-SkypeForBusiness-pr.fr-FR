---
title: Réinitialisation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: 812391eda436906020c41b14a53c8ea18c4b1aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241324"
---
# <a name="reset-call-admission-control"></a>Réinitialisation du contrôle d’admission des appels

Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
  
### <a name="to-reset-cac"></a>Pour réinitialiser le CAC

1. Ouvrez le générateur de topologie.
    
2. Cliquez avec le bouton droit sur le nœud site, puis cliquez sur **modifier les propriétés**.
    
3. Sous **paramètre de contrôle d’admission des appels**, assurez-vous que l’option **activer le contrôle d’admission des appels** est activée. 
    
4. Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le pool Skype entreprise Server 2019 d’hébergement CAC, puis cliquez sur **OK**.
    
5. Publiez la topologie.
    

