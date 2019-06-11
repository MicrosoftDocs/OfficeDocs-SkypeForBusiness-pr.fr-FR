---
title: 'Lync Server 2013: configuration de stratégies utilisateur pour l’archivage dans Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3921956949f38390277328495398970203993377
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Configuration de stratégies utilisateur pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-10_

L’activation ou la désactivation de l’archivage pour des utilisateurs spécifiques hébergés sur Lync Server 2013 nécessite la création et la configuration d’une ou plusieurs stratégies utilisateur, puis l’application de la stratégie appropriée à des utilisateurs ou groupes d’utilisateurs spécifiques. Les stratégies utilisateur remplacent les stratégies de site et globales, mais uniquement pour les utilisateurs hébergés sur Lync Server 2013.

Les utilisateurs sont toujours hébergés sur Lync Server. Si l’intégration de Microsoft Exchange est activée, les utilisateurs dont les boîtes aux lettres se trouvent dans Microsoft Exchange Server 2013 n’ont pas besoin d’avoir leurs stratégies d’archivage dans le gestion de Lync Server. Ces utilisateurs dotés de l’archivage seront gérés par Exchange en blocage.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie des stratégies globales, de site et d’utilisateur, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.

<div>


> [!NOTE]  
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, Exchange stratégies de conservation inaltérable Déterminez si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013. Pour ces utilisateurs, l’archivage nécessite que leurs boîtes aux lettres soient placées sur place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Création et configuration des stratégies utilisateur pour l’archivage dans Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Appliquer une stratégie d’archivage Lync Server à un utilisateur dans Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

