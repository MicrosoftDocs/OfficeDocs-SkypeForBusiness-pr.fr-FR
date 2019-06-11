---
title: Création et configuration des stratégies utilisateur pour l’archivage dans Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3adccda55d1ae033acf52d64b093e73fe81dad10
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>Création et configuration des stratégies utilisateur pour l’archivage dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-09_

Pour activer ou désactiver l’archivage pour des utilisateurs spécifiques hébergés sur Lync Server, vous devez d’abord créer une stratégie d’utilisateur, puis l’appliquer à un ou plusieurs utilisateurs ou groupes d’utilisateurs. Pour plus d’informations sur l’application de stratégies utilisateur à des utilisateurs et groupes d’utilisateurs spécifiques, voir [appliquer une stratégie d’archivage Lync Server à un utilisateur dans Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie pour les stratégies globales, de site et d’utilisateur, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation sur les opérations.

<div>


> [!NOTE]
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, Exchange stratégies de conservation inaltérable Déterminez si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées sur le blocage sur place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>Pour configurer une stratégie d’archivage pour les utilisateurs hébergés sur Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server 2013, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **stratégie**d’archivage.

4.  Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.

5.  Dans **Nouvelle stratégie d’archivage**, procédez comme suit :
    
      - Dans **Nom**, spécifiez le nom de la stratégie utilisateur.
    
      - Dans **Description**, entrez des informations décrivant la stratégie utilisateur (par exemple, stratégie utilisateur pour le service juridique).
    
      - Pour contrôler l’archivage des communications internes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications internes**.
    
      - Pour contrôler l’archivage des communications externes de la stratégie utilisateur, activez ou désactivez la case à cocher **Archiver les communications externes**.

6.  Cliquez sur **Valider**.

Une stratégie utilisateur ne s’applique qu’aux utilisateurs auxquels vous affectez la stratégie. Pour plus d’informations sur l’application d’une stratégie utilisateur à des utilisateurs spécifiques, voir [appliquer une stratégie d’archivage Lync Server à un utilisateur dans Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md) dans la documentation de déploiement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

