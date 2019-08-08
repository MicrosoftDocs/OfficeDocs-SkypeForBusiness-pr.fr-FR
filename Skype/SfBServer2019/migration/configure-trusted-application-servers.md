---
title: Configuration des serveurs d’applications approuvées
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dans un environnement mixte, si vous créez un nouveau serveur d’applications de confiance, vous devez définir le pool de prochains tronçons comme un pool Skype entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool 2019 de Skype entreprise Server apparaissent dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.
ms.openlocfilehash: b715cd7f3f067c5e54dbc085350fcc7f96b5c4be
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239297"
---
# <a name="configure-trusted-application-servers"></a>Configuration des serveurs d’applications approuvées

Dans un environnement mixte, si vous créez un nouveau serveur d’applications de confiance, vous devez définir le pool de prochains tronçons comme un pool Skype entreprise Server 2019. Dans un environnement mixte, le pool hérité et le pool 2019 de Skype entreprise Server apparaissent dans la liste déroulante. La sélection du pool hérité n’est pas prise en charge.
  
> [!IMPORTANT]
> Si vous migrez un serveur d’application de confiance, vous devez également mettre à jour la version de UCMA que vous utilisez. Si vous créez un nouveau pool d’applications approuvé pour Skype entreprise Server 2019, vous devez mettre à jour UCMA vers la version incluse dans Skype entreprise Server 2019 ou la dernière version disponible. 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Sélectionner Skype entreprise Server 2019 comme tronçon suivant lors de la création d’un serveur d’applications de confiance

1. Ouvrez le générateur de topologie.
    
2. Dans le volet de gauche, cliquez avec le bouton droit sur **serveurs d’applications de confiance** , puis cliquez sur **nouveau pool d’applications de confiance**.
    
3. Entrez le **nom de domaine complet (FQDN)** du pool d’applications de confiance et sélectionnez s’il s’agit d’un serveur unique ou d’un serveur multiple. 
    
4. Cliquez sur **Suivant**.
    
5. Dans la page **Sélectionner le tronçon suivant** , dans la liste, sélectionnez le pool frontal Skype entreprise Server 2019. 
    
6. Cliquez sur **Terminer**.
    
7. Sélectionnez le nœud supérieur **Skype entreprise Server**, puis, dans le menu **action** , sélectionnez **publier**.
    
    Vérifiez que le **pool d’applications approuvé** a été créé avec succès et est associé au pool frontal approprié. 
    

