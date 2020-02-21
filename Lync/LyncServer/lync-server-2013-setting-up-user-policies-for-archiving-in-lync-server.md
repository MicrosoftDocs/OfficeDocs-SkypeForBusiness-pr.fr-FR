---
title: 'Lync Server 2013 : configuration des stratégies utilisateur pour l’archivage dans Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e032dd276ee41a711ded56d33a065d515b182ab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Configuration des stratégies utilisateur pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

L’activation ou la désactivation de l’archivage pour des utilisateurs spécifiques hébergés sur Lync Server 2013 nécessite la création et la configuration de stratégies utilisateur, puis l’application de la stratégie appropriée à des utilisateurs ou groupes d’utilisateurs spécifiques. Les stratégies utilisateur remplacent les stratégies de site et les stratégies globales, mais uniquement pour les utilisateurs hébergés sur Lync Server 2013.

Les utilisateurs sont toujours hébergés dans Lync Server. Si l’intégration de Microsoft Exchange est activée, les utilisateurs dont les boîtes aux lettres sont dans Microsoft Exchange Server 2013 n’ont pas besoin de gérer les stratégies d’archivage dans Lync Server. Ces utilisateurs disposant d’un archivage seront gérés par la conservation inaltérable d’Exchange.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

<div>


> [!NOTE]  
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de conservation inaltérable d’Exchange contrôlent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013. Pour ces utilisateurs, la fonctionnalité d’archivage nécessite que leurs boîtes aux lettres soient placées dans une archive permanente. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Création et configuration de stratégies utilisateur pour l’archivage dans Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Application d’une stratégie d’archivage Lync Server à un utilisateur dans Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

