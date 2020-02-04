---
title: Déploiement de clients Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Déploiement de clients Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Après avoir migré des utilisateurs vers Lync Server 2013, procédez comme suit :

1.  Utilisez le filtre de version du client sur le nouveau serveur Lync Server 2013 pour autoriser uniquement les clients sur lesquels les mises à jour les plus récentes sont installées pour la connexion.

2.  Le cas échéant, configurez les paramètres de stratégie de groupe requis pour le démarrage du client. Pour plus d’informations, reportez-vous à la rubrique [configuration de stratégies d’amorçage client dans Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement. La configuration de ces paramètres n’est nécessaire que si vous voulez modifier les stratégies d’amorçage client existantes ou si vous voulez définir de nouvelles stratégies de démarrage de client. Si vous n’envisagez pas de configurer des stratégies d’amorçage client ou si vous souhaitez que les stratégies d’amorçage de clients héritées restent en vigueur, aucune action n’est nécessaire.

3.  Configurez d’autres stratégies utilisateur et client pour des utilisateurs ou des groupes d’utilisateurs spécifiques à l’aide du panneau de configuration de Lync Server 2013, de Lync Server 2013 Management Shell, ou les deux. Pour plus d’informations, reportez-vous aux [paramètres nouveaux et modifiés pour Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) dans la documentation de planification.

4.  Déployez la dernière version de clients 2013 Lync Server avec les mises à jour les plus récentes. Pour plus d’informations, reportez-vous à la section [déploiement de clients et d’appareils dans Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) dans la documentation de déploiement.

5.  Facultatif Si votre organisation nécessite le mode de confidentialité de présence Enhanced de Lync Server 2013, une fois la migration terminée, définissez une règle de stratégie de version de client pour empêcher les versions de client antérieure de se connecter. Activez ensuite le mode de confidentialité Enhanced Presence.
    
    <div>
    

    > [!IMPORTANT]  
    > N’activez pas le mode de confidentialité de la présence améliorée de Lync 2013 tant que tous les utilisateurs sur un pool de serveurs donné n’ont pas installé la version la plus récente du client.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

