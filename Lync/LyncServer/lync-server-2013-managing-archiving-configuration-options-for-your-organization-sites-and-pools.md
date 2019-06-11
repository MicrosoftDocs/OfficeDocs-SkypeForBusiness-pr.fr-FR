---
title: 'Lync Server 2013: gestion des options de configuration de l’archivage pour votre organisation, vos sites et vos pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10efbf23a503364de7034651d94ced43a8d7b750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Dans Lync Server 2013 panneau de configuration, vous utilisez des configurations d’archivage pour spécifier la façon dont l’archivage est implémenté. Cela inclut les configurations d’archivage suivantes:

  - Configuration globale créée par défaut lors du déploiement de Lync Server 2013.

  - Configurations facultatives de niveau de site et de niveau groupe que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des groupes spécifiques.

Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Dans Lync Server 2013 panneau de configuration, vous pouvez utiliser la page **configuration** de l’archivage du groupe **archivage et surveillance** pour gérer les configurations au niveau global, au niveau du site et au niveau du pool. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, déploiement documentation ou documentation sur les opérations.

<div>


> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il convient d’activer l’archivage des communications internes, pour les communications externes ou pour tous les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes et externes. Si vous utilisez l’intégration de Microsoft Exchange, vous devez activer et configurer Exchange 2013 pour la prise en charge de l’archivage de tous les utilisateurs hébergés sur Exchange 2013 qui ont reçu leurs boîtes aux lettres dans le blocage sur place.<BR>Avant de procéder à l’archivage, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, si vous le souhaitez, pour des sites et des groupes spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

**Pour afficher les informations de configuration de l’archivage à l’aide des cmdlets Windows PowerShell**

  - Vous pouvez afficher les informations de configuration de l’archivage à l’aide de Windows PowerShell et de l’applet **de cmdlet Get-CsArchivingConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».
    
    Dans Lync Server Management Shell, utilisez la commande suivante pour afficher les informations relatives à l’ensemble de vos paramètres de configuration de l’archivage:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Créer une configuration d’archivage dans Lync Server 2013 pour gérer l’archivage de sites ou de groupes spécifiques](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Activation ou désactivation de l’archivage des sessions de messagerie instantanée ou de conférence dans Lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Activation ou désactivation de la suppression de données archivées dans Lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Activation ou désactivation du mode critique dans Lync Server 2013 pour bloquer ou autoriser des sessions de messagerie instantanée et de conférence Web en cas d’échec de l’archivage](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Activation ou désactivation de l’intégration de Lync Server 2013 avec le stockage Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Suppression d’une configuration d’archivage dans Lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion de l’archivage Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

