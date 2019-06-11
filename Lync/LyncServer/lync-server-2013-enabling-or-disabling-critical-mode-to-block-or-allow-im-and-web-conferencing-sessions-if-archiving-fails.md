---
title: 'Lync Server 2013: activation ou désactivation du mode critique pour bloquer ou autoriser des sessions de messagerie instantanée et de conférence Web en cas d’échec de l’archivage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a>Activation ou désactivation du mode critique dans Lync Server 2013 pour bloquer ou autoriser des sessions de messagerie instantanée et de conférence Web en cas d’échec de l’archivage

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Dans Lync Server 2013 panneau de configuration, vous utilisez des configurations d’archivage pour activer et désactiver le mode critique. Cela inclut les configurations d’archivage suivantes:

  - Configuration globale créée par défaut lors du déploiement de Lync Server 2013.

  - Configurations facultatives de niveau de site et de niveau groupe que vous pouvez créer et utiliser pour spécifier la façon dont l’archivage est implémenté pour des sites ou des groupes spécifiques.

Vous définissez initialement des configurations d’archivage lors du déploiement de l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir fonctionnement [de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, déploiement documentation ou documentation sur les opérations.

<div>


> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage pour spécifier s’il convient d’activer l’archivage pour les communications internes, pour les communications externes ou pour les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes et externes. Avant l’activation de l’archivage dans toutes les stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, si vous le souhaitez, pour des sites et des groupes spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuration et affectation de stratégies d’archivage dans Lync Server 2013</A> dans la documentation de déploiement.<BR>Si vous décidez après le déploiement de l’archivage sur lequel vous souhaitez utiliser l’intégration Exchange Server pour stocker les données et fichiers d’archivage sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de la base de données SQL Server de votre topologie. Pour ce faire, vous devez utiliser le générateur de topologie. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-changing-archiving-database-options.md">modifier les options de base de données d’archivage dans Lync Server 2013</A> dans la documentation sur les opérations



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a>Pour activer ou désactiver le blocage des sessions de messagerie instantanée et de conférence Web en cas d’échec de l’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **surveillance et archivage**, puis cliquez sur **configuration de l’archivage**.

4.  Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit :

5.  Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a>Activation et désactivation du mode critique à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez activer ou désactiver le mode critique à l’aide de l’applet de la cmdlet **Set-CsArchivingConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-enable-critical-mode"></a>Pour activer le mode critique

  - Pour activer le mode Critical, définissez la valeur de la propriété BlockOnArchiveFailure sur true ($True). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a>Pour désactiver le mode critique

  - Pour désactiver le mode Critical, définissez la valeur de la propriété BlockOnArchiveFailure sur false ($False). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modification des options de base de données d’archivage dans Lync Server 2013](lync-server-2013-changing-archiving-database-options.md)  


[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

