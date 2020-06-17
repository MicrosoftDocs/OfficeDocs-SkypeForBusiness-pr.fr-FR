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
description: Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool du tronçon suivant en tant que pool Skype entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool Skype entreprise Server 2019 apparaissent dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753944"
---
# <a name="configure-trusted-application-servers"></a>Configurer les serveurs d’applications approuvées

Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool du tronçon suivant en tant que pool Skype entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool Skype entreprise Server 2019 apparaissent dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.
  
> [!IMPORTANT]
> Si vous migrez un serveur d’applications approuvées, vous devez également mettre à jour la version de UCMA que vous utilisez. Si vous créez un nouveau pool d’applications approuvées pour Skype entreprise Server 2019, vous devez mettre à jour UCMA vers la version incluse avec Skype entreprise Server 2019 ou la dernière version disponible. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Sélectionnez Skype entreprise Server 2019 comme tronçon suivant lors de la création d’un serveur d’applications approuvées

1. Ouvrez le Générateur de topologie.
    
2. Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications approuvées** , puis cliquez sur **nouveau pool d’applications approuvées**.
    
3. Entrez le **nom de domaine complet du pool** du pool d’applications approuvées et sélectionnez s’il s’agira d’un serveur unique ou d’un serveur multiple. 
    
4. Cliquez sur **Suivant**.
    
5. Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Skype entreprise Server 2019. 
    
6. Cliquez sur**Terminer**.
    
7. Sélectionnez le nœud supérieur **Skype entreprise Server**, puis, dans le menu **action** , sélectionnez **publier**.
    
    Vérifiez que le **pool d’applications approuvées** a été créé avec succès et qu’il est associé au pool frontal correct. 
    

