---
title: 'Lync Server 2013 : application d’une stratégie d’archivage Lync Server à un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cad9784eb2c50662bfedc460cb0dbc8c892206c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504931"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>Application d’une stratégie d’archivage Lync Server à un utilisateur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Après avoir créé une stratégie utilisateur Lync Server, vous devez l’appliquer à des utilisateurs ou à des groupes d’utilisateurs qui sont hébergés sur Lync Server 2013 avant qu’elle ne prenne effet. Pour plus d’informations sur la création de stratégies utilisateur pour des utilisateurs spécifiques, voir [Creating and Configuring User Policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) dans la documentation de déploiement.

Pour plus d’informations sur le fonctionnement des stratégies d’archivage, notamment la hiérarchie pour les stratégies globale, de site et utilisateur, voir [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

<div>


> [!NOTE]  
> Pour configurer et utiliser l’archivage, vous devez tout d’abord déployer l’archivage. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-deploying-archiving.md">déploiement de l’archivage dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies de blocage Exchange In-Place déterminent si l’archivage est activé pour les utilisateurs hébergés sur Exchange 2013 et que leurs boîtes aux lettres sont placées en conservation In-Place. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies d’archivage dans Lync Server 2013 lors de l’utilisation de l’intégration d’Exchange Server</A> dans la documentation de déploiement.<BR>Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-configuring-archiving-options.md">Configuration des options d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>Pour appliquer une stratégie d’archivage Lync Server à un utilisateur

1.  À partir d’un compte utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Lync Server 2013. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server 2013, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur Lync Server** , sous **stratégie d’archivage**, sélectionnez la stratégie utilisateur d’archivage que vous souhaitez appliquer.
    
    <div>
    

    > [!NOTE]  
    > Les paramètres <STRONG> &lt; automatiques &gt; </STRONG> appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.

    
    </div>

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

