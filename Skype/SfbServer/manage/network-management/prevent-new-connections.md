---
title: Empêcher les nouvelles connexions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: d6f0bfcace21a0383b51a81ee37d60d3f7e227d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397688"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Empêcher les nouvelles connexions à Skype Entreprise Server pour la maintenance du serveur


Skype Entreprise Server vous permet de mettre un serveur hors connexion (par exemple, pour appliquer des mises à niveau logicielles ou matérielles) sans perte de service aux utilisateurs.

Quand vous spécifiez l’option qui empêche toute nouvelle connexion ou tout nouvel appel sur un serveur appartenant à un pool, Lync Server n’accepte plus de nouvelles connexions, ni de nouveaux appels une fois cette option implémentée. Quand un serveur empêche toute nouvelle connexion, il autorise ses sessions sur des connexions existantes à se poursuivre, jusqu’à ce qu’elles se terminent normalement. Une fois toutes les sessions existantes parvenues à terme, le serveur est prêt à être mis hors connexion.

Lorsque vous empêchez de nouvelles connexions à un serveur frontal, certaines fonctionnalités et services Skype Entreprise Server reposent sur l’équilibrage de charge DNS pour s’assurer qu’il fonctionne correctement. Si vous n’utilisez pas l’équilibrage de charge DNS sur le pool, il se peut que les connexions via ces services ne soient pas ré-acheminées vers d’autres serveurs pendant la période où le serveur empêche de nouvelles connexions, et par conséquent, lorsque le serveur est mis hors connexion, certaines sessions et appels peuvent être interrompus. Les fonctionnalités qui s’appuient sur l’équilibrage de charge DNS pour s’assurer que cette option fonctionne correctement sont les suivantes :

  - Attendant

  - application d’annonce de conférence

  - Application Response Group

  - application d’annonce

  - application de parcage d’appel

Pour plus d’informations sur l’équilibrage de charge DNS, consultez [la liste des conditions requises pour l’équilibrage de charge](../../plan-your-deployment/network-requirements/load-balancing.md).

En plus d’empêcher les nouvelles connexions pour tous les services sur un serveur exécutant Skype Entreprise Server, vous pouvez également empêcher les nouvelles connexions pour les services Skype Entreprise Server individuels. Par exemple, cette méthode est utile lorsque vous devez appliquer une mise à jour Skype Entreprise Server qui ne nécessite pas l’arrêt de l’intégralité du serveur. Veuillez noter que lorsque vous interdisez les connexions pour un service, vous devez sélectionner un service groupé et affiché dans la liste des services Windows. Par exemple, le service Skype Entreprise Server Front-End et l’agent de collecte de données pour la surveillance sont des services Skype Entreprise Server distincts, mais dans la liste des services Windows, ils sont consolidés et affichés en tant que Skype Entreprise Server frontal service. Vous pouvez empêcher les nouvelles connexions pour le service frontal Skype Entreprise Server, mais vous ne pouvez pas empêcher les nouvelles connexions pour ces deux services Skype Entreprise Server sous-jacents séparément.

> [!IMPORTANT]
> Lorsque vous configurez un serveur pour empêcher les nouvelles connexions, puis le redémarrez, par défaut, le serveur accepte immédiatement les connexions. Si vous ne voulez pas que cela se produise, configurez le serveur pour qu’il ne soit suspendu et redémarré que manuellement avant de redémarrer le serveur.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Pour empêcher les nouvelles connexions à Skype Entreprise Server

1.  Ouvrez une session sur l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Ouvrez la console en ligne Services **: cliquez sur** Démarrer, pointez sur Tous les **programmes,** pointez sur Outils d’administration **,** puis cliquez sur **Services**.

3.  Dans la liste, double-cliquez sur Skype Entreprise Server Windows service auquel vous souhaitez empêcher de nouvelles connexions.

4.  Dans la boîte de dialogue Propriétés, sous **État du service : Démarré**, cliquez sur **Suspendre**.

5.  La méthode facultative et recommandée consiste à cliquer sur **Manuel**, en regard de **Type de démarrage**.
    
    > [!IMPORTANT]
    > Lorsque vous configurez un serveur pour empêcher les nouvelles connexions, puis le redémarrez, par défaut, le serveur accepte immédiatement les connexions. Si vous ne voulez pas que cela se produise, configurez le serveur pour qu’il ne soit suspendu et redémarré que manuellement avant de redémarrer le serveur.
