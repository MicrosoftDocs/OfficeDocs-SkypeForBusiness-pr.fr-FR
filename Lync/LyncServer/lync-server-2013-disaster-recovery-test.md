---
title: 'Skype Entreprise Server 2015 : test de récupération d’urgence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Test de récupération d’urgence dans Skype Entreprise Server 2015

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-01-26_

Effectuez une récupération du système pour un serveur de pool Lync Server 2013 pour tester votre processus de récupération d’urgence documenté. Ce test simule une défaillance matérielle complète d’un serveur et permet de s’assurer que les ressources, les plans et les données sont disponibles pour la récupération. Essayez d’alterner l’angle du test chaque mois afin que votre organisation teste chaque fois la défaillance d’un autre serveur ou d’un autre équipement.

Notez que le calendrier des tests de récupération d'urgence de votre organisation varie. Il est très important que les tests de récupération d’urgence ne soient ni ignorés ni négligés.

<div>


Exportez votre topologie, les stratégies et les paramètres de configuration de Lync Server 2013 vers un fichier. Ce fichier peut, entre autres, être utilisé pour restaurer ces informations dans le magasin central de gestion après une mise à niveau, une défaillance matérielle ou un autre problème ayant entraîné une perte de données.

Importez votre topologie et vos paramètres de configuration de Lync Server 2013 vers le magasin de gestion central ou vers l’ordinateur local, comme illustré dans les commandes suivantes:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Pour sauvegarder les données de Lync Server 2013 de production, procédez comme suit:

  - Sauvegardez les bases de données RTC et LCSLog à l’aide du processus de sauvegarde SQL Server standard pour vider la base de données sur un fichier ou un appareil de vidage de bande.

  - Sauvegardez les données dans un fichier ou sur une bande à l’aide de l’application de sauvegarde tierce.

  - Créez un export XML de la base de données RTC intégrale à l’aide de l’applet de commande Export-CsUserData.

  - Sauvegardez le contenu d’une réunion et les journaux de conformité à l’aide de la sauvegarde du système de fichiers ou d’un utilitaire de sauvegarde/restauration tiers.

  - Utilisez l’outil de ligne de commande Export-CsConfiguration pour sauvegarder les paramètres de Lync Server 2013.

La première étape de la procédure de basculement comporte un déplacement forcé des utilisateurs du pool de production vers le pool de récupération d’urgence.

Il s’agit d’un déplacement forcé, car le pool de production n’est pas disponible pour accepter le déplacement des utilisateurs.

Le processus de déplacement d’utilisateur de Lync Server 2013 est une modification apportée à un attribut sur l’objet de compte d’utilisateur, en plus de la mise à jour d’un enregistrement dans la base de données SQL RTC.

Ces données peuvent être restaurées par le biais des deux procédures suivantes :

  - La base de données RTC peut être restaurée à partir de l’appareil de vidage de sauvegarde original à partir du serveur SQL de production en utilisant le processus de restauration standard de SQL Server, ou à l’aide d’une utilitaire de sauvegarde/restauration tierce.

  - Les données de contact des utilisateurs peuvent être restaurées avec l’utilitaire DBIMPEXP.exe à l’aide du fichier XML créé à partir de l’export SQL Server de production.

Une fois ces données restaurées, les utilisateurs peuvent se connecter efficacement au pool Lync Server 2013 de reprise après sinistre et fonctionner comme d’habitude.

Pour permettre aux utilisateurs de se connecter au pool de reprise après sinistre Lync Server 2013, une modification de l’enregistrement DNS sera requise.

Le pool Lync Server 2013 de production sera référencé par les clients à l’aide de la configuration automatique et des enregistrements SRV DNS de:

  - SRV: \_SIP. \_TLS. \<Domain\> /CNAME: SIP. \<Domain (domaine)\>

  - CNAME: SIP. \<Domain\> /CVC-pool-1. \<Domain (domaine)\>

Pour faciliter le basculement, cet enregistrement CNAME doit être mis à jour de manière à référencer le nom de domaine complet (FQDN) DROCSPool :

  - CNAME: SIP. \<Domain\> /DROCSPool. \<Domain (domaine)\>

  - SIP. \<Domain (domaine)\>

  - AV.\<Domain\>

  - webconf. \<Domain (domaine)\>

  - OCSServices. \<Domain (domaine)\>

<div>


> [!IMPORTANT]  
> Pour des procédures d’administration et de gestion détaillées, reportez-vous à la rubrique <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">sauvegarde et restauration de Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets de sauvegarde et de haute disponibilité dans Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Importation-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Sauvegarde et restauration de Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Gestion de la récupération d’urgence, de la haute disponibilité et du service de sauvegarde de Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

