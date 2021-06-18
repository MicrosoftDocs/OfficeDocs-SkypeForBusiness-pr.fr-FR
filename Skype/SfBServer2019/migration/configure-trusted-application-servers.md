---
title: Configurer les serveurs d’applications approuvées
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
description: Dans un environnement mixte, si vous créez un serveur d’applications approuvé, vous devez définir le pool du saut suivant comme pool Skype Entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool Skype Entreprise Server 2019 apparaissent dans la liste liste. La sélection du pool hérité n’est pas prise en charge.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753944"
---
# <a name="configure-trusted-application-servers"></a>Configurer les serveurs d’applications approuvées

Dans un environnement mixte, si vous créez un serveur d’applications approuvé, vous devez définir le pool du saut suivant comme pool Skype Entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool Skype Entreprise Server 2019 apparaissent dans la liste de listes. La sélection du pool hérité n’est pas prise en charge.
  
> [!IMPORTANT]
> Si vous migrez un serveur d’applications approuvé, vous devez également mettre à jour la version d’UCMA que vous utilisez. Si vous créez un nouveau pool d’applications de confiance pour Skype Entreprise Server 2019, vous devez mettre à jour UCMA vers la version incluse dans Skype Entreprise Server 2019 ou la dernière version disponible. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Sélectionner Skype Entreprise Server 2019 comme saut suivant lors de la création d’un serveur d’applications de confiance

1. Ouvrez le Générateur de topologie.
    
2. Dans le volet gauche, cliquez avec le bouton droit sur **Serveurs d’applications** de confiance et cliquez sur **Nouveau pool d’applications de confiance.**
    
3. Entrez le **nom de pool du** pool d’applications de confiance et sélectionnez s’il s’appliquera à un ou plusieurs serveurs. 
    
4. Cliquez sur **Suivant**.
    
5. Dans la page **Sélectionner le saut suivant,** dans la liste, sélectionnez le pool frontal Skype Entreprise Server 2019. 
    
6. Cliquez sur **Terminer**.
    
7. Sélectionnez le nœud supérieur **Skype Entreprise Server** et, dans le menu **Action,** sélectionnez **Publier.**
    
    Vérifiez que le **pool d’applications** fiables a bien été créé et qu’il est associé au pool frontal correct. 
    

