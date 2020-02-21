---
title: Déployer les clients Lync Server 2013
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
ms.openlocfilehash: 313386b58c3bd455070c992a59e42270872532cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Déployer les clients Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

Après avoir migré les utilisateurs vers Lync Server 2013, procédez comme suit :

1.  Utilisez le filtre de version du client sur le nouveau serveur Lync Server 2013 pour autoriser uniquement les clients sur lesquels les mises à jour les plus récentes sont installées pour se connecter.

2.  Si nécessaire, configurez les paramètres de stratégie de groupe qui sont requises pour le démarrage du client. Pour plus d’informations, reportez-vous à la rubrique [Configuring Client Bootstrapper Policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) dans la documentation de déploiement. La configuration de ces paramètres est nécessaire seulement si vous voulez définir des nouvelles stratégies de démarrage du client. Si vous ne prévoyez pas de configurer des stratégies de démarrage du client ou si vous voulez que les stratégies de démarrage du client héritées restent en vigueur, aucune action n’est alors requise.

3.  Configurez d’autres stratégies utilisateur et client pour des utilisateurs ou des groupes d’utilisateurs spécifiques à l’aide du panneau de configuration Lync Server 2013, de l’environnement de gestion de Lync Server 2013 ou des deux. Pour plus d’informations, reportez-vous aux [paramètres nouveaux et modifiés pour Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) dans la documentation de planification.

4.  Déployez la dernière version des clients Lync Server 2013 avec les mises à jour cumulatives les plus récentes. Pour plus d’informations, voir [Deploying clients and Devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) dans la documentation de déploiement.

5.  Module Si votre organisation requiert le mode de confidentialité Enhanced presence de Lync Server 2013, une fois la migration terminée, définissez une règle de stratégie de version de client pour empêcher les versions antérieures du client de se connecter. Activez ensuite le mode de confidentialité améliorée de la présence.
    
    <div>
    

    > [!IMPORTANT]  
    > N’activez pas le mode de confidentialité Enhanced presence de Lync 2013 tant que tous les utilisateurs d’un pool de serveurs donné n’ont pas installé les versions de client les plus récentes.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

