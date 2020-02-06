---
title: Empêcher les nouvelles connexions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: c2df1c491384f8a248f70b67880511a2d496c173
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817453"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Blocage de nouvelles connexions à Skype entreprise Server pour la maintenance du serveur


Skype entreprise Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à jour logicielles ou matérielles) sans aucune perte de service aux utilisateurs.

Lorsque vous spécifiez l’option permettant d’éviter de nouvelles connexions ou appels vers un serveur d’un pool, il cesse de prendre de nouvelles connexions et appels dès que vous implémentez cette option. Ces nouvelles connexions et appels sont routés par le biais d’autres serveurs du pool. Un serveur qui empêche de nouvelles connexions autorise la poursuite de ses sessions sur les connexions existantes jusqu’à ce qu’il se termine de façon naturelle. Lorsque toutes les sessions existantes sont terminées, le serveur est prêt à être déconnecté.

Lorsque vous interdisez de nouvelles connexions à un serveur frontal, certains services et fonctionnalités Skype entreprise Server dépendent de l’équilibrage de charge DNS pour s’assurer qu’elle fonctionne correctement. Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, les connexions par le biais de ces services ne peuvent pas être redirigées vers d’autres serveurs au cours de la période pendant laquelle le serveur empêche les nouvelles connexions, et par conséquent, lorsque le serveur est hors connexion, certaines sessions et appels peuvent être garantir. Les fonctionnalités qui dépendent de l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes :

  - Intendant

  - application d’annonce de conférence

  - application Response Group

  - application d’annonce

  - application de parcage d’appel

Pour plus d’informations sur l’équilibrage de charge DNS, voir [exigences d’équilibrage de charge](../../plan-your-deployment/network-requirements/load-balancing.md).

Outre la prévention de nouvelles connexions pour tous les services sur un serveur exécutant Skype entreprise Server, vous pouvez également interdire de nouvelles connexions pour les services Skype entreprise Server individuels. Par exemple, cette méthode est utile dans le cas où vous devez appliquer une mise à jour de Skype entreprise Server qui ne nécessite pas l’arrêt de l’intégralité du serveur. Notez que lorsque vous interdisez les connexions d’un service, vous devez sélectionner un service tel qu’il est groupé et affiché dans la liste des services Windows. Par exemple, le service frontal de Skype entreprise Server et l’agent de collecte des données pour la surveillance sont des services Skype entreprise Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés sous la forme de Skype entreprise Server front-end service. Vous pouvez éviter de nouvelles connexions au service frontal Skype entreprise Server, mais vous ne pouvez pas empêcher les nouvelles connexions de ces deux services sous-jacents de Skype entreprise Server séparément.

> [!IMPORTANT]
> Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage. Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Pour éviter de nouvelles connexions à Skype entreprise Server

1.  Connectez-vous à l’ordinateur local en tant que membre du groupe administrateurs.

2.  Ouvrez la console enfichable Services : cliquez sur **Démarrer**, pointez sur **tous les programmes**, sur **Outils d’administration**, puis cliquez sur **services**.

3.  Dans la liste, double-cliquez sur le service Windows Skype entreprise Server sur lequel vous voulez empêcher les nouvelles connexions.

4.  Dans la boîte de dialogue Propriétés, sous **État du service : démarré**, cliquez sur **suspendre**.

5.  Si vous le souhaitez, mais que vous avez le choix, en regard de **type de démarrage**, cliquez sur **Manuel**.
    
    > [!IMPORTANT]
    > Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis que vous redémarrez le serveur, par défaut, le serveur commence immédiatement à accepter de nouvelles connexions après son démarrage. Pour éviter ce problème, configurez le serveur de façon à ce qu’il ne s’interrompe qu’après le redémarrage du serveur.
