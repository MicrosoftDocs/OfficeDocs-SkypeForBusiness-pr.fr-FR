---
title: Réinitialisation du contrôle d’admission des appels
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307097"
---
# <a name="reset-call-admission-control"></a>Réinitialisation du contrôle d’admission des appels

Si un pool frontal hérité héberge le contrôle d’admission des appels (CAC), vous devez déplacer l’hébergement CAC vers un pool Skype entreprise Server 2019 avant de pouvoir supprimer le pool frontal hérité.
  
### <a name="to-reset-cac"></a>Pour réinitialiser le CAC

1. Ouvrez le générateur de topologie.
    
2. Cliquez avec le bouton droit sur le nœud site, puis cliquez sur **modifier les propriétés**.
    
3. Sous **paramètre de contrôle d’admission des appels**, assurez-vous que l’option **activer le contrôle d’admission des appels** est activée. 
    
4. Sous **pool frontal pour exécuter le contrôle d’admission des appels (CAC)**, sélectionnez le pool Skype entreprise Server 2019 d’hébergement CAC, puis cliquez sur **OK**.
    
5. Publiez la topologie.
    

