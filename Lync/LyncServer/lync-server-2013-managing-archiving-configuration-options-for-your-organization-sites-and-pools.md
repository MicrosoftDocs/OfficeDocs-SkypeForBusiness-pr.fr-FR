---
title: "Gest. des opt. de conf. de l’arch. ds LS 2013 pr vos org., sites et pools"
TOCtitle: "Gest. des opt. de conf. de l’arch. ds LS 2013 pr vos org., sites et pools"
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204802(v=OCS.15)
ms:contentKeyID: 49296871
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools

 

_**Dernière rubrique modifiée :** 2012-11-01_

Dans le Panneau de configuration Lync Server 2013, vous utilisez les configurations de l’archivage pour spécifier son implémentation. Les configurations d’archivage sont les suivantes :

  - une configuration globale créée par défaut lorsque vous déployez Lync Server 2013 ;

  - des configurations facultatives au niveau du site et du pool que vous pouvez créer et utiliser pour spécifier le mode d’implémentation de l’archivage de sites ou pools spécifiques.

Vous définissez les configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations une fois le déploiement terminé. Dans le Panneau de configuration Lync Server 2013, accédez à la page **Configuration de l’archivage** dans le groupe **Archivage et surveillance** pour gérer les configurations aux niveaux global, du site et de l’utilisateur. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage afin de spécifier si l’archivage doit être activé pour les communications internes, les communications externes ou les deux, pour tous les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Si vous utilisez l’intégration de Microsoft Exchange, vous devez activer et configurer Exchange 2013 pour à prendre en charge l’archivage pour tous les utilisateurs hébergés sur Exchange 2013 dont les boîtes aux lettres ont été placées en archive permanente.<br />
Avant d’activer l’archivage, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuration et affectation des stratégies d’archivage</a> dans la documentation de déploiement.

**Pour afficher les informations de configuration de l’archivage à l’aide des applets de commande Lync Server Management Shell**

  - Vous pouvez aussi afficher les informations de configuration de l’archivage dans Windows PowerShellLync Server à l’aide de l’applet de commande **Get-CsArchivingConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).
    
    Dans Lync Server Management Shell, utilisez la commande suivante pour afficher les informations relatives à tous vos paramètres de configuration de l’archivage :
    
        Get-CsArchivingConfiguration

## Dans cette section

  - [Création d’une configuration d’archivage pour gérer l’archivage pour des sites ou des pools spécifiques](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Activation ou désactivation de l’archivage de sessions de messagerie instantanée ou de conférence](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Activation ou désactivation de la purge des données archivées](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Activation ou désactivation du mode critique pour bloquer ou autoriser des sessions de messagerie instantanée et de conférences web en cas d’échec de l’archivage](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Activation ou désactivation de l’envoi d’une notification d’exclusion relative à l’archivage aux partenaires fédérés dans Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Activation ou désactivation de l’intégration avec le stockage Exchange](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Suppression d’une configuration d’archivage](lync-server-2013-deleting-an-archiving-configuration.md)

## Voir aussi

#### Autres ressources

[Gestion de l’archivage Lync Server 2013](lync-server-2013-managing-archiving.md)

