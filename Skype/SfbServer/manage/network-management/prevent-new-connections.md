---
title: Empêcher les nouvelles connexions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 682e3e986e55b879036217e8ca1ed558666a67de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913341"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Empêcher les nouvelles connexions à Skype pour Business Server pour la maintenance du serveur


Skype pour Business Server permet de prendre un serveur hors ligne (par exemple, pour appliquer les mises à jour de logiciel ou matériel) sans perte de service pour les utilisateurs.

Lorsque vous spécifiez l’option pour empêcher les nouvelles connexions ou des appels vers un serveur dans un pool, elle cesse d’accepter des appels et les nouvelles connexions dès que vous implémentez cette option. Ces nouvelles connexions et les appels sont routés par les autres serveurs du pool. Un serveur qui empêche les nouvelles connexions permet à ses sessions sur les connexions existantes pour continuer jusqu'à la fin de leur naturellement. Lorsque toutes les sessions existantes sont terminées, le serveur est prêt à être mis hors connexion.

Lorsque vous empêchez les nouvelles connexions à un serveur frontal, certains Skype pour les services et fonctionnalités Business Server s’appuient sur équilibrage DNS pour vous assurer qu’il fonctionne correctement. Si vous n’utilisez pas le DNS équilibrage de charge sur le pool, les connexions via ces services ne soient pas réacheminées vers d’autres serveurs pendant la période que le serveur est empêcher les nouvelles connexions, et donc lorsque le serveur est mis hors connexion des sessions et les appels peuvent être interrompue. Les fonctionnalités qui reposent sur la charge DNS équilibrée pour vous assurer que cette option fonctionne correctement sont les suivantes :

  - Intendant

  - application d’annonce de conférence

  - application Response Group

  - application d’annonce

  - application de parcage d’appel

Pour plus d’informations sur l’équilibrage de charge DNS, voir [Configuration requise de l’équilibrage de charge](../../plan-your-deployment/network-requirements/load-balancing.md).

En plus d’empêcher les nouvelles connexions pour tous les services sur un serveur exécutant Skype pour Business Server, vous pouvez également empêcher les nouvelles connexions Skype individuel pour les services Business Server. Par exemple, cette méthode est utile dans une situation où vous devez appliquer un Skype pour une mise à jour Business Server qui ne nécessite pas l’ensemble du serveur d’être arrêté. Notez que lorsque vous empêchez les connexions pour un seul service, vous devez sélectionner un service lorsqu’elles sont regroupé et affichée dans la liste des services Windows. Par exemple, le Skype pour le service Business Server frontal et l’agent de collection de données de surveillance sont Skype distinct pour les services Business Server, mais dans la liste des services Windows, ils sont consolidées et affichées sous forme de la Skype pour Business Server frontal service. Vous pouvez empêcher les nouvelles connexions pour le Skype pour le service Business serveur frontal, mais vous ne pouvez pas empêcher les nouvelles connexions pour ces deux Skype de sous-jacent individuelles pour les services Business Server séparément.

> [!IMPORTANT]
> Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis redémarrez le serveur, par défaut le serveur commence immédiatement après son démarrage accepter de nouvelles connexions. Pour éviter ce problème, définissez le serveur aux seules suspendre et reprendre manuellement, avant de redémarrer le serveur.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>Pour empêcher les nouvelles connexions à Skype Business Server

1.  Ouvrez une session l’ordinateur local en tant que membre du groupe Administrateurs.

2.  Ouvrez la console du composant logiciel enfichable Services : cliquez sur **Démarrer**, pointez sur **Tous les programmes**, pointez sur **Outils d’administration**, puis cliquez sur **Services**.

3.  Dans la liste, double-cliquez sur le Skype pour le service Business Server Windows à laquelle vous souhaitez empêcher les nouvelles connexions.

4.  Dans la boîte de dialogue Propriétés, sous **état du Service : démarré**, cliquez sur **Suspendre**.

5.  Si vous le souhaitez, mais recommandé, en regard de **type de démarrage**, cliquez sur **manuel**.
    
    > [!IMPORTANT]
    > Lorsque vous définissez un serveur pour empêcher les nouvelles connexions, puis redémarrez le serveur, par défaut le serveur commence immédiatement après son démarrage accepter de nouvelles connexions. Pour éviter ce problème, définissez le serveur aux seules suspendre et reprendre manuellement, avant de redémarrer le serveur.
