---
title: Création et configuration de stratégies utilisateur pour l’archivage dans Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40425957d472da2d31d91472634f268dde5b8c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504671"
---
# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Création et configuration de stratégies utilisateur pour l’archivage dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Pour activer ou désactiver l’archivage pour des utilisateurs spécifiques hébergés sur Lync Server, vous devez d’abord créer une stratégie utilisateur, puis l’appliquer à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Pour plus d’informations sur l’application de stratégies d’utilisateur à des utilisateurs et groupes d’utilisateurs spécifiques, voir [Applying a Lync Server Archiving Policy to a User in Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

<div>


> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de blocage Exchange In-Place déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Pour configurer une stratégie d’archivage pour les utilisateurs hébergés sur Lync Server

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, reportez-vous à la rubrique [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.

4.  Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.

5.  Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
      - Dans **Nom**, spécifiez le nom de la stratégie utilisateur.
    
      - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).
    
      - Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.

6.  Cliquez sur **Valider**.

Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie. Pour plus d’informations sur l’application d’une stratégie utilisateur à des utilisateurs spécifiques, reportez-vous [à l’application d’une stratégie d’archivage Lync Server à un utilisateur dans Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

