---
title: Gestion de l’archivage des communications internes et externes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891318ba677891916af678b74365026d20d69016
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Gestion de l’archivage des communications internes et externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Dans Lync Server 2013, vous utilisez les stratégies d’archivage pour activer et désactiver l’archivage des communications internes et des communications externes si vous n’utilisez pas l’intégration de Microsoft Exchange ou si vous avez des utilisateurs qui ne sont pas hébergés sur Exchange 2013 avec leurs boîtes aux lettres placées sur Blocage sur place. Cela inclut les stratégies d’archivage suivantes :

  - Stratégie globale créée par défaut lors du déploiement de Lync Server 2013.

  - Stratégies de niveau de site et de niveau utilisateur facultatives que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des utilisateurs spécifiques.

Vous définissez initialement des stratégies d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des stratégies après le déploiement. Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la page de **stratégie d’archivage** du groupe **archivage et surveillance** pour gérer les stratégies au niveau global, au niveau du site et au niveau de l’utilisateur. Si vous intégrez le stockage de votre serveur Lync au stockage 2013 Exchange, les stratégies d’utilisateur Exchange sont prioritaires sur les stratégies d’archivage de Lync Server 2013.

Pour plus d’informations sur l’implémentation de stratégies, y compris la hiérarchie des stratégies, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.

<div>


> [!NOTE]
> Pour contrôler l’implémentation de l’archivage, vous devez spécifier les options de configuration de l’archivage, par exemple pour archiver les messages instantanés ou les conférences, utiliser le mode Critical et les options de purge. Par défaut, aucune option n’est activée dans la configuration de l’archivage global ni dans toute configuration d’archivage de site ou de pool. Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage des communications internes ou externes dans les stratégies d’archivage. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">la section gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</A> dans la documentation des opérations.<BR>Si vous activez l’intégration de Microsoft Exchange pour votre déploiement, les stratégies Exchange contrôlent la configuration de l’archivage pour les utilisateurs qui sont hébergés sur Exchange 2013 et ont leurs boîtes aux lettres placées sur place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques](lync-server-2013-create-archiving-policy-sites-users.md)

  - [Modification d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour votre organisation, certains sites ou des utilisateurs](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Appliquer une stratégie d’archivage aux utilisateurs de Lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Configuration de stratégies d’archivage dans Lync Server 2013 lors de l’utilisation d’une intégration Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Suppression d’une stratégie d’archivage dans Lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

