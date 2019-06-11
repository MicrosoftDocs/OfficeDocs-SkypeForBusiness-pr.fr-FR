---
title: 'Lync Server 2013: application d’une stratégie d’archivage Lync Server à un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295f1a0370372d937b07a38eab51cd43d0ef9f5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846914"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Appliquer une stratégie d’archivage Lync Server à un utilisateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-10_

Après la création d’une stratégie d’utilisateur Lync Server, vous devez l’appliquer à des utilisateurs ou groupes d’utilisateurs qui sont hébergés sur Lync Server 2013 avant de pouvoir prendre effet. Pour plus d’informations sur la création de stratégies utilisateur pour des utilisateurs spécifiques, voir [création et configuration des stratégies utilisateur pour l’archivage dans Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) dans la documentation de déploiement.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, y compris la hiérarchie des stratégies globales, de site et d’utilisateur, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou les opérations.

<div>


> [!NOTE]  
> Pour configurer et utiliser l’archivage, vous devez tout d’abord déployer cette fonction. Pour plus d’informations, reportez-vous à la section déploiement <A href="lync-server-2013-deploying-archiving.md">de l’archivage dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, Exchange stratégies de conservation inaltérable Déterminez si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées sur le blocage sur place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">configuration de stratégies d’archivage dans Lync server 2013 lors de l’utilisation d’une intégration Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez spécifier toutes les options appropriées dans les configurations d’archivage avant de procéder à l’archivage. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Pour appliquer une stratégie d’archivage Lync Server à un utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server 2013, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Lync Server** sous **stratégie**d’archivage, sélectionnez la stratégie d’utilisateur d’archivage que vous voulez appliquer.
    
    <div>
    

    > [!NOTE]  
    > Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.

    
    </div>

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

