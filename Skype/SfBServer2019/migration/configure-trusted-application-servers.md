---
title: Configurer des serveurs d’applications approuvées
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool à un Skype pour Business Server 2019 pool du tronçon suivant. Dans un environnement mixte, à la fois le pool hérité et le Skype pour Business Server 2019 pool s’affichent dans la liste déroulante. Sélectionnez le pool hérité n’est pas pris en charge.
ms.openlocfilehash: d1c79e044145a4739cf1b7bfb3992320be1e4ab3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027745"
---
# <a name="configure-trusted-application-servers"></a>Configurer des serveurs d’applications approuvées

Dans un environnement mixte, si vous créez un nouveau serveur d’applications approuvées, vous devez définir le pool à un Skype pour Business Server 2019 pool du tronçon suivant. Dans un environnement mixte, à la fois le pool hérité et le Skype pour Business Server 2019 pool s’affichent dans la liste déroulante. Sélectionnez le pool hérité n’est pas pris en charge.
  
> [!IMPORTANT]
> Si vous migrez un serveur d’applications approuvées, vous devez également mettre à jour la version d’UCMA que vous utilisez. Si vous créez un nouveau Pool d’applications approuvées pour Skype pour Business Server 2019, vous devez mettre à jour UCMA pour la version qui est incluse avec Skype pour Business Server 2019 ou la version la plus récente. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Sélectionnez Skype pour Business Server 2019 comme tronçon suivant lors de la création d’un serveur d’applications approuvées

1. Ouvrez le Générateur de topologie.
    
2. Dans le volet gauche, cliquez sur **serveurs d’applications approuvées** , cliquez sur **Nouveau Pool d’applications approuvées**.
    
3. Entrez le **Nom complet du Pool** du pool d’applications approuvées et indiquez s’il s’agira serveur unique ou de plusieurs serveurs. 
    
4. Cliquez sur **Suivant**.
    
5. Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le Skype pour Business Server 2019 un pool frontal. 
    
6. Cliquez sur **Terminer**.
    
7. Sélectionnez le nœud supérieur **Skype pour Business Server**, dans le menu **Action** , sélectionnez **Publier**.
    
    Vérifiez que le **Pool d’applications approuvées** a été créé avec succès et associé au pool frontal correct. 
    

